<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';

  let isMounted = false;

  onMount(() => {
    isMounted = true;
  });

  const servers = [
    { id: 1, name: 'Server 1', status: 'Online' },
    { id: 2, name: 'Server 2', status: 'Offline' },
    { id: 3, name: 'Server 3', status: 'Online' },
  ];

  const addServer = () => {
    servers.push({ id: servers.length + 1, name: `Server ${servers.length + 1}`, status: 'Offline' });
  };

  const updateServer = (id, status) => {
    const server = servers.find((server) => server.id === id);
    if (server) {
      server.status = status;
    }
  };

  const deleteServer = (id) => {
    servers.splice(servers.findIndex((server) => server.id === id), 1);
  };
</script>

<div class="container">
  <h1>Name of Project</h1>
  <button on:click={addServer}>Add Server</button>
  <ul>
    {#each servers as server}
      <li>
        <span>{server.name}</span>
        <span>Technology</span>
        <span>Idea & Innovation</span>
        <span>Learning</span>
        <span class={server.status === 'Online' ? 'online' : 'offline'}>{server.status}</span>
        <button on:click={() => updateServer(server.id, server.status === 'Online' ? 'Offline' : 'Online')}>Toggle Status</button>
        <button on:click={() => deleteServer(server.id)}>Delete Server</button>
      </li>
    {/each}
  </ul>
</div>

<style>
  .container {
    max-width: 800px;
    margin: 40px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  .online {
    color: green;
  }

  .offline {
    color: red;
  }
</style>