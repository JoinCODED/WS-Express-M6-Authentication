1. Note that we can create many `students` with the same `name`! Every `student` should have a unique `name`. In our `Student` model, we will add a field called unique and give the property args the value true:

```js
name: {
   type: DataTypes.STRING,
   allowNull: false,
   unique: {
      args: true,
   },
},
```

2. Let's try again. Hmmm, the error message is not clear and so not cute! We can customize the error message with the property `msg`:

```js
name: {
   type: DataTypes.STRING,
   allowNull: false,
   unique: {
      args: true,
      msg: "Name already exists"
   },
},
```

3. Try again to create a `student`, isn't it weird that the hashed password is returned? Replace `newStudent` with a message that indicates a `student` is created.

```js
const newStudent = await Student.create(req.body);
res.status(201).json({ message: 'Student created successfully' });
```
