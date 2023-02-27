# finlock-assingment

import React, { useState } from 'react';
import { Container, Form, FormGroup, Label, Input, Button } from 'reactstrap';

const LoginPage = () => {
  const [username, setUsername] = useState('');
  const [password, setPassword] = useState('');

  const handleUsernameChange = (event) => {
    setUsername(event.target.value);
  };

  const handlePasswordChange = (event) => {
    setPassword(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    console.log(`Username: ${username}, Password: ${password}`);
    // TODO: Handle authentication logic here
  };

  return (
    <Container className="mt-5">
      <Form onSubmit={handleSubmit}>
        <FormGroup>
          <Label for="username">Username:</Label>
          <Input
            type="text"
            name="username"
            id="username"
            value={username}
            onChange={handleUsernameChange}
            placeholder="Enter your username"
          />
        </FormGroup>
        <FormGroup>
          <Label for="password">Password:</Label>
          <Input
            type="password"
            name="password"
            id="password"
            value={password}
            onChange={handlePasswordChange}
            placeholder="Enter your password"
          />
        </FormGroup>
        <Button type="submit" color="primary">Login</Button>
      </Form>
    </Container>
  );
};

export default LoginPage;








db.users.insertOne({
  username: "johndoe",
  geolocation: {
    latitude: 37.7749,
    longitude: -122.4194
  },
  loginTime: new Date(),
  osName: "Windows 10",
  browserName: "Chrome",
  sessionTime: 3600 // seconds
})





// Find all users who logged in from California
db.users.find({ "geolocation.state": "CA" })

// Find the most recent login time for a specific user
db.users.findOne({ username: "johndoe" }, { loginTime: 1, _id: 0 }, { sort: { loginTime: -1 }})
