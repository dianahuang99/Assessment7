- BUG #1: in the auth.js route, line 50 need to await the result so we don't just get a promise

- BUG #2: in users.js route, line 18 router.get("/") in the docstring, it only wants to basic info so I removed the extra info

- BUG #3: in users.js route, line 68 router.patch get rid of requireAdmin because requireLogin already checks if user is admin

- BUG #4: in users.js route, line 111 router.delete added "await" User.delete(req.params.username) so that the app doesn't crash when I try to delete a non-existent user

- BUG #5: in user.js model, line 115 I added the word "throw" in throw new ExpressError("No such user", 404)

- BUG #6: in middleware auth.js, I used jwt.verify instead of jwt.decode this will raise an error if an invalid token is passed in jwt.verify(token, SECRET_KEY)
