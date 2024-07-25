GitHub Actions:
GitHub Actions is an automation tool that lets you run tasks when certain events happen in your GitHub repository. Think of it like a robot assistant that can do things for you automatically.

Main parts of a GitHub Actions workflow YAML file:

1. Name:
   This is like the title of your automation recipe. It tells you and others what this workflow does.

```yaml
name: My First Workflow
```

2. On (Triggers):
   This section tells the robot when to wake up and do its job. It could be when you push code, create a pull request, or even on a schedule.

```yaml
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
```

3. Jobs:
   Jobs are the main tasks your robot needs to do. Each job is like a separate to-do list.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
```

4. Steps:
   Steps are the individual actions within a job. Think of them as detailed instructions for your robot.

```yaml
steps:
  - uses: actions/checkout@v2
  - name: Run a one-line script
    run: echo Hello, world!
```

5. Uses:
   This tells the robot to use a pre-made action, like grabbing your code or setting up a programming language.

6. Run:
   This is where you tell the robot exactly what commands to run, like building your code or running tests.

Let's put it all together in a simple example:

```yaml
name: Greet and Test

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  greet-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Say hello
        run: echo "Hello, GitHub Actions!"
      - name: Run a simple test
        run: |
          echo "Running tests..."
          # Your test commands would go here
          echo "Tests completed!"
```

This workflow does the following:

1. It's named "Greet and Test"
2. It runs when you push or make a pull request to the main branch
3. It has one job called "greet-and-test" that runs on the latest Ubuntu
4. The job has three steps:
   - Check out the code
   - Say hello
   - Run a simple (pretend) test
