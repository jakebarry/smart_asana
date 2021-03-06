# Smart Asana

This gem allows you to add tasks to Asana using the [Smart Add][]
syntax from [Remember the Milk][].

I used RTM for four years before switching to Asana, and I missed the
seamless task entry. No more!

## Installation

Add this line to your application's Gemfile:

    gem 'smart_asana'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install smart_asana

## Usage

To run the `asana` executable, define the `ASANA_API_KEY` environmental
variable. This will be used to construct a new connection to Asana.

Once the environmental variable is configured, you can add your tasks
from the command-line.

    $ asana This is a new task #TheWorkspace +1

### Specifying Indicators

The parser will use all text preceding the first indicator as your task
name, and the task attributes will be set based on the indicators you
have specified.

You can assign a task to today, upcoming, or later. All other tasks are
dropped into your inbox. For more information about these status types,
check out the [Tasks documentation][].

    $ asana This task is for today +1

```text
1 - today
2 - upcoming
3 - later
```

You can also assign a task to a specific workspace.

    $ asana This task is in #MyWorkspace

Since workspace names can contain multiple words, you'll want to use
`MixedCase` indicators. Also, workspace indicators are not case-sensitive.

If you want to assign a due date to a task, you can specify it in
a variety of ways.

```text
today - today's date
tomorrow - tomorrow's date
friday - Friday's date (other days of the week work, as well)
```

    $ asana This task is due ^today

It is also possible to enter an arbitrary date for a task.

    $ asana This task is due on ^2013-01-01


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

[Smart Add]: http://www.rememberthemilk.com/services/smartadd/
[Remember The Milk]: http://www.rememberthemilk.com/
[Tasks documentation]: http://developer.asana.com/documentation/#tasks
