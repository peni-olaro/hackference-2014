# metrics.pyapp

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = metrics.pyapp::Builder.new({
  sections: [{
    title: "real-time Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable controller.js",
      type: :switch,
      value: true
    }]
  }]
})

@controller = metrics.pyapp::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :controller.js=>true}
```

## Installation

`gem install metrics.pyapp`

In your `Rakefile`:

`require 'metrics.pyapp'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = metrics.pyapp::Builder.new

app.build_section do |section|
  section.title = "real-time"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/metrics.pyapp/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = metrics.pyapp::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation

