pipeline {
    agent any

        stage('Build') {
            steps {
                // Build this project.
                sh 'dotnet restore src/Web/Web.csproj'
                sh 'dotnet tool restore --configfile src/Web/.config/dotnet-tool.json'
                sh 'dotnet publish src/Web/Web.csproj -c Release -o out -r linux-x64 --self-contained'
                // Tell Web+ how to start this application.
                sh 'echo "Web: ASPNETCORE_ENVIRONMENT=Development . /Web" > out/Procfile'
                // Package this project.
                sh 'cd out && zip -qr webplus-dotnet-demo.zip .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'wpctl env:apply -y --package out/webplus-dotnet-demo.zip --category "ASP.NET Core" --app webplus-dotnet-demo --env test-env --create-on-absent'
            }
        }
    }
}
