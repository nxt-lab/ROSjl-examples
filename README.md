# ROSjl-examples
Examples of using Julia for ROS.

## Set up Julia for ROS

These are the steps for setting up Julia for ROS.  They were tested on ROS Melodic on Ubuntu 18.04, but should work on ROS Kinetic and probably newer versions of ROS 1.

1. Fully set up ROS, including `rospy`.
2. Install Julia for Linux: [download link](https://julialang.org/downloads/), follow the [platform instructions](https://julialang.org/downloads/platform/).
3. Locate the version of Python used for ROS (actually for `rospy`). Typically it's `python2` or `python2.7`. Do not use `python` since it might be symlinked to a different version of Python not used by ROS. One way to confirm this is to open a Python script in one of the official `rospy` tutorials (use the `roscd` command) and check the shebang line at the top.
4. Install `PyCall` in Julia with the version of Python for ROS:
    1. Start Julia (`julia`)
    2. Type in the command line: `ENV["PYTHON"] = "<the Python command used for ROS>"`. For example: `ENV["PYTHON"] = "python2"`.
    3. Install and build `PyCall`, either with the Package Management console (press `]` in the Julia command line) or with the following commands:
    ```julia
    Pkg.add("PyCall")
    Pkg.build("PyCall")
    ```
5. Install `RobotOS.jl` for Julia: run `Pkg.add("RobotOS")` or use the Package Management.
6. Test it by running `using RobotOS`.
7. Follow the tutorial / examples and read the documentation at <https://jdlangs.github.io/RobotOS.jl/latest/>.  The Git site is at <https://github.com/jdlangs/RobotOS.jl>. 
