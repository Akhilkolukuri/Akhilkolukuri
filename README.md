- 👋 Hi, I’m @Akhilkolukuri
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Akhilkolukuri/Akhilkolukuri is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

Level 1:

- users.js (component):

jsx
import React, { useState, useEffect } from 'react';
import axios from 'axios';

function Users() {
  const [users, setUsers] = useState([]);
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');

  useEffect(() => {
    axios.get('(link unavailable)')
      .then(response => {
        setUsers(response.data);
      });
  }, []);

  const handleSubmit = (event) => {
    event.preventDefault();
    const userData = { name, email };
    axios.post('(link unavailable)', userData)
      .then(response => {
        setUsers([...users, response.data]);
        setName('');
        setEmail('');
      });
  };

  return (
    <div>
      <h1>Users</h1>
      <table>
        <thead>
          <tr>
            <th>Name</th>
            <th>Email</th>
          </tr>
        </thead>
        <tbody>
          {users.map((user) => (
            <tr key={(link unavailable)}>
              <td>{user.name}</td>
              <td>{user.email}</td>
            </tr>
          ))}
        </tbody>
      </table>
      <form onSubmit={handleSubmit}>
        <label>
          Name:
          <input type="text" value={name} onChange={(event) => setName(event.target.value)} />
        </label>
        <br />
        <label>
          Email:
          <input type="email" value={email} onChange={(event) => setEmail(event.target.value)} />
        </label>
        <br />
        <button type="submit">Add User</button>
      </form>
    </div>
  );
}

export default Users;


Level 2:

- users.js (component):

jsx
import React, { useState, useEffect } from 'react';
import { Table, Button, Form, Input } from 'antd';

function Users() {
  const [users, setUsers] = useState([]);
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');

  useEffect(() => {
    axios.get('(link unavailable)')
      .then(response => {
        setUsers(response.data);
      });
  }, []);

  const handleSubmit = (event) => {
    event.preventDefault();
    const userData = { name, email };
    axios.post('(link unavailable)', userData)
      .then(response => {
        setUsers([...users, response.data]);
        setName('');
        setEmail('');
      });
  };

  return (
    <div>
      <h1>Users</h1>
      <Table columns={[
        {
          title: 'Name',
          dataIndex: 'name',
        },
        {
          title: 'Email',
          dataIndex: 'email',
        },
      ]} data={users} />
      <Form onSubmit={handleSubmit}>
        <Form.Item label="Name">
          <Input value={name} onChange={(event) => setName(event.target.value)} />
        </Form.Item>
        <Form.Item label="Email">
          <Input value={email} onChange={(event) => setEmail(event.target.value)} />
        </Form.Item>
        <Form.Item>
          <Button type="primary" htmlType="submit">Add User</Button>
        </Form.Item>
      </Form>
    </div>
  );
}

export default Users;


