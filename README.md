# ZacJR-71.github.io

const retropieProfiles = require('retropie-profiles-server')

module.exports = retropieProfiles(async function (req, res, login) {
  const name = 'Zac'
  const id = 1

  // you may emit the "login" event on `res` to log in a user
  const hosts = login({
    // Make sure you use a unique ID associated with the user.
    // This would usually be a user ID or database ID
    id: id,

    // This is the user name that is displayed in the Login status page.
    // Only used for display purposes
    name: name
  })

  // you have complete control over the HTTP request and response
  res.setHeader('Content-Type', 'text/plain')
  res.end(`You have been logged in on ${hosts.join(', ')}`)
})
