Customisations for GitLab.
--------

GitLab home dir : `/opt/gitlab/embedded/service/gitlab-rails/`

How to: After changing corrsponding files run these commands as root or use sudo.

Make `assets` dir writable.

```
chmod -R 1777  /opt/gitlab/embedded/service/gitlab-rails/app/assets
chmod -R 1777 /opt/gitlab/embedded/service/gitlab-rails/public/assets/
```

Compile the assets.

```
gitlab-rake assets:clean RAILS_ENV=production && gitlab-rake assets:precompile RAILS_ENV=production && gitlab-rake cache:clear RAILS_ENV=production
```

Restart gitlab.

```
gitlab-ctl restart
```

Watch for any errors.

```
gitlab-ctl tail
```