Getting started
===============

Once you have installed the library the fun can begin! 
To get started import the library in your python project like so::

    from AoE2ScenarioParser.scenarios.aoe2_de_scenario import AoE2DEScenario

| Define the file you will be reading from and where you will be writing your new file to. 
| Please note: *It is recommended to not overwrite the file you will be reading for backup reasons.* 

::

    input_path = "File/Path/To/Your/Input/kFile.aoe2scenario"
    output_path = "File/Path/To/Your/Output/File.aoe2scenario"

Now create the ``Scenario`` object with the filename as parameter. Or create a default scenario::

    scenario = AoE2DEScenario.from_file(input_path)

You can now edit to your heart's content. Every aspect of the scenario is seperated in managers. 
Not all parts are currently supported. The following list shows the current support and use of 
all available managers:

- **trigger_manager**: The trigger manager is used for creating, editing and removing Triggers, Conditions, Effects and Variables.
- **unit_manager**: The unit manager is used for creating, editing and removing Units. This includes buildings and heroes etc.
- **map_manager**: The map manager is used for changing terrain, elevation or simply getting coordinates for certain types.

You can access all managers like so::

    trigger_manager = scenario.trigger_manager

After you're done editing, you can save your work and write it to an ``aoe2scenario`` file::

    scenario.write_to_file(output_path)
