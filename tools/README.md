#
Standalone tools

OpenPlotter has a chance to integrate independent programs which can share some of the OpenPlotter features. This was done to be open for add-ons done by advanced users and to keep OpenPlotter simple for newcomers.

There are implemented some standalone tools in OpenPlotter core maintaned by developers and a demo tool to make it easier to start. You can look at the code of these tools and build your own app/addon.

### Adding a tool

Openplotter is able to work with external Python scripts.

There is a demo script in *~/.openplotter/tools/demo_tool/demo_tool.py*

To enable the demo tool open the OpenPlotter configuration file in *~/.openplotter/openplotter.conf*. Go to section [TOOLS] and you will see something like this:

```
[TOOLS]
py = [['Analog ads1115', 'put analog values to SignalK', 'analog_ads1115', '0'], ['Analog Firmata', 'put analog values to SignalK', 'oppymata', '0']]
```

The syntax of this array is:

```
[TOOLS]
py = [['title', 'description', 'folder', 'startup'], [...], [...], [...]]
```

* **title** is the name you want to have in OpenPlotter Tools menu.
* **description** is a short sentence describing your app.
* **folder** is the name of the folder where your app lives. The main script of your app must be named like your folder (folder.py)
* **startup** will be '1' if you want your app to start at startup or '0' if not.

To enable the demo tool you have to add this array to the array _py_ in the [TOOLS] section of *~/.openplotter/openplotter.conf* file:

```
['Demo tool', 'You can use this app to start your own apps', 'demo_tool', '0']
```

Save the file and go to the OpenPlotter Tools menu. You should see now the option "Demo tool".

Once selected, a new window will be open with these options:

* **Settings**. If you have defined a config file for your app, it will be open with a text editor.
* **Start**. This option will start your app.
* **Stop**. This option will stop your app.
* **Cancel**. This option will close this window.

If you want to add your own tool you have just to create a folder in *~/.openplotter/tools* folder and create a python script named like your new folder (*~/.openplotter/tools/mytool/mytool.py*). Then edit the [TOOLS] section in *~/.openplotter/openplotter.conf* file just the same way you did for the demo tool.

See the source of the demo tool to know how to manage config files, manage the OpenPlotter config file, interact with Signal K server or access to OpenPlotter classes.

Let us know if you make any tool that we can add to OpenPlotter core.

