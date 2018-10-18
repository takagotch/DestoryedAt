### DestroyedAt
---
https://github.com/DavyJonesLocker/ruby-destroyed_at

```
gem 'destroyed_at'

CREATE INDEX ON users WHERE destroyed_at IS NULL;
CREATE INDEX ON users WHERE destroyed_at IS NOT NULL;

```


```ruby
class User < ActiveRecord::Base
  include DestroyedAt
end

class ActiveRecord::Base
  include DestroyedAt
end

class User < ActivaRecord::Base
  include DestroyedAt
end
user = User.create
user.destroy
user.destroyed_at

class User < ActiveRecord::Base
  include DestroyedAt
end
user = User.create
user.destroy
user.restore
user.destroyed_at

class User < ActiveRecord::Base
  before_restore :before_restore_action
  after_restore :after_restore_action
  around_restore :around_restore_action
  private
  def before_restore_action
  end
  def after_restore_action
  end
  def around_restore_action
    # before around
    yield
    # after around
  end
end

validates :email, uniqueness: { conditions: -> { where(destroyed_at: nil) } }


```


```
```

