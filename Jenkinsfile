echo pwd()

node {
	stage 'Checkout'
		checkout scm

	stage 'Build'
		//bat 'nuget restore ConsoleApplication1/ConsoleApplication1.sln'
		bat "\"${tool 'MSBuild 15.0'}\\msbuild.exe\" ConsoleApplication1/ConsoleApplication1.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"

	stage 'Archive'
		archive 'ConsoleApplication1/ConsoleApplication1/bin/Release/**'

}
