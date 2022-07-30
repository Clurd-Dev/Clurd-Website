<script>
import { onMount } from 'svelte/internal';
let Lightbox;
onMount(async() => {
  Lightbox = await (await import('bs5-lightbox')).default;
});
</script>
<div class="row">
    <div class="col-2">
      <nav id="navbar-example3" class="h-100 flex-column align-items-stretch pe-4 border-end">
        <nav class="nav nav-pills flex-column">
          <a class="nav-link" href="#item-1">Install Clurd on Windows</a>
          <nav class="nav nav-pills flex-column">
            <a class="nav-link ms-3 my-1" href="#item-1-1">Install .NET Core Runtime</a>
            <a class="nav-link ms-3 my-1" href="#item-1-2">Configure and install Clurd</a>
          </nav>
          <a class="nav-link" href="#item-3">Install Clurd on Linux</a>
          <nav class="nav nav-pills flex-column">
            <a class="nav-link ms-3 my-1" href="#item-3-1">Install all dependencies</a>
            <a class="nav-link ms-3 my-1" href="#item-3-2">Run the one-line installer</a>
            <a class="nav-link ms-3 my-1" href="#configure">Configure Clurd</a>
            <a class="nav-link ms-3 my-1" href="#create">Create a service for Clurd in init.d</a>

          </nav>
        </nav>
      </nav>
    </div>
  
    <div class="col">
      <div data-bs-spy="scroll" data-bs-target="#navbar-example3" data-bs-smooth-scroll="true" class="scrollspy-example-2" tabindex="0">
        <div id="item-1">
          <h4>Install Clurd on Windows</h4>
          <p>The installation in Windows is divided in more points:</p>
          <ul>
            <li>Install .Net Core Runtime</li>
            <li>Configure Clurd</li>
          </ul>
          <h4>Let's start!</h4>
          <br/>
        </div>
        <div id="item-1-1">
          <h5>Install .NET Core Runtime on Windows</h5>
          <p>.You can use a packet manager such Chocolatey or Winget(Windows 11). This is the command for Chocolatey:</p>
          <ul>
            <li>choco install dotnet-6.0-runtime</li>
          </ul>
          <p>If all go correct this is the result</p>
          <a href="/chocoinstall.png" data-toggle="lightbox">
          <img src="/chocoinstall.png" alt="Choco install" class="img-fluid"/>
          </a>
          <p>If you don't want to use a packet manager, you can install .NET 6 from this <a href="https://dotnet.microsoft.com/en-us/download/dotnet/6.0">link</a></p>
          <p>You must install .NET Runtime and ASP.NET Core runtime to run Clurd</p>
        </div>
        <div id="item-1-2">
          <h5>Configure and install Clurd</h5>
          <p>Download the last Clurd installer at this <a href="https://github.com/Clurd-Dev/Clurd.NET/releases">link</a>. Click on setup.exe in Github Assets and then run it.</p>
          <a href="/clurdsetup.png" data-toggle="lightbox">
          <img src="/clurdsetup.png" alt="Setup" class="img-fluid"/>
          </a>
          <p>After the setup finished, run Clurd App</p>
          <p>Click on Select executable of Clurd and go to the path where Clurd is installed, should be C:\Program Files (x86)\Clurd\Clurd Server\Clurd\bin\Release\net6.0\publish</p>
          <p>Now, press on edit config button and write the path where Clurd should gets files and we can also modify username and password which should be in <a href="http://www.md5.cz/">md5 crypt</a>(the default password is 1234 in md5 crypt)</p>
          <a href="/clurdapp.png" data-toggle="lightbox">
          <img src="/clurdapp.png" alt="App" class="img-fluid"/>
          </a>
          <p>Now start server and all the work is done</p>
        </div>
        <div id="item-3">
          <h4>Install Clurd on Linux</h4>
          <p>The installation of Clurd in Linux isn't easy and maybe in future will be improved</p>
          <ul>
            <li>Install all dependencies</li>
            <li>Run the one-line installer</li>
            <li>Configure Clurd</li>
            <li>Create a service for Clurd in init.d</li>
          </ul>
        </div>
        <div id="item-3-1">
          <h5>Install all dependencies</h5>
          <p>To build Clurd we need .NET Core, git and NodeJS</p>
          <p>To install .NET Core follow this <a href="https://docs.microsoft.com/en-US/dotnet/core/install/linux">guide</a></p>
          <p>Install Git is usually easy, the command is: "package manager(APT, pacman, yum...)" install git</p>
          <p>Install NodeJS depend on your distribuition, you couldn't use the version from Node Version Manager or similar cause this method give problem to .NET Core. You should follow any guide for your distribution on internet.
            Node Version must be 16 or higher.
          </p>
        </div>
        <div id="item-3-2">
          <h5>Run the one-line installer</h5>
          <p>Clurd have a builder script to download and build Clurd on your PC. The installation path of Clurd is the path where you run the script, maybe you should create a folder only for Clurd and his file</p>
          <p>To run the one-line installed do this command: <a href="#0">curl -s https://raw.githubusercontent.com/Clurd-Dev/Clurd.NET/main/Clurd/Clurd/LinuxInstaller/install.sh | sudo bash</a></p>
          <p>If all script run correctly, this is the final output</p>
          <a href="/linuxdone.png" data-toggle="lightbox">
          <img src="/linuxdone.png" alt="Linuxdone" class="img-fluid"/>
          </a>
          <br/>
          <br/>
        </div>
        <div id="configure">
          <h5>Configure Clurd</h5>
          <p>To configure Clurd, you need to go in the Clurd compiled folder: <a href="#0">cd Clurd.NET/Clurd/Clurd/bin/Release/net6.0/publish</a></p>
          <p>Then you need to edit the configuration file called config.json</p>
          <p>The command is <a href="#0">nano config.json</a></p>
          <p>Now we can edit the path where Clurd serve and upload files then we can modify the username and the password, the password must be in <a href="http://www.md5.cz/">md5 crypt</a>. The default password is 1234 with admin user</p>
          <a href="/nanoclurd.png" data-toggle="lightbox">
          <img src="/nanoclurd.png" alt="Edit path with nano" class="img-fluid"/>
          </a>
          <br/>
          <br/>
          <p>When we finish press CTRL + X and press Y to save the changes</p>
        </div>
        <div id="create">
          <h5>Create a service for Clurd in init.d</h5>
          <p>To run Clurd easily we need to create a init.d script</p>
          <p>Clurd have a init.d template where we must insert the username of our Linux profile and the path of Clurd executable</p>
          <p>To download template we do this command: <a href="#0">curl -o /etc/init.d/Clurd https://raw.githubusercontent.com/Clurd-Dev/Clurd.NET/main/Clurd/Clurd/LinuxInstaller/clurd.sh</a></p>
          <p>Now we need to change some data, so open an editor on init.d script: <a href="#0">nano /etc/init.d/Clurd</a></p>
          <p>We change USER with our user and PATHTOCLURD with the path to Clurd executable</p>
          <p>The final file should be similar to this</p>
          <a href="/initcomplete.png" data-toggle="lightbox">
            <img src="/initcomplete.png" alt="Complete init.d script" class="img-fluid"/>
          </a>
          <br/>
          <br/>
          <p>To try this script start Clurd: <a href="#0">/etc/init.d/Clurd start</a></p>
          <p>If all is ok, we could navigate to localhost:5000 and we should see Clurd home page</p>
        </div>
      </div>
    </div>
  </div>

  <style>
    img{
      padding: 10px;
    }
    div{
      padding: 10px;
    }
  </style>