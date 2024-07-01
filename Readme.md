# OSI Model Implementation in Rust


## Project Overview

 This project is an implementation of the OSI (Open Systems Interconnection) model in Rust, designed to provide a comprehensive understanding of both the OSI model and the Rust programming language. The OSI model is a conceptual framework used to understand and implement network protocols in seven layers: Physical, Data Link, Network, Transport, Session, Presentation, and Application.


## Features

- **Physical Layer**: Handles raw data transmission over network interfaces.
- **Data Link Layer**: Manages Ethernet frames, MAC addresses, and error detection.
- **Network Layer**: Implements IP packet handling, routing algorithms, and IP fragmentation.
- **Transport Layer**: Supports TCP/UDP segments, connection management, flow control, and congestion control.
- **Session Layer**: Manages sessions, including initiation, maintenance, and termination.
- **Presentation Layer**: Provides data translation, encryption, and compression.
- **Application Layer**: Implements common application protocols like HTTP.


## Getting Started

### Installation

1. Clone the Repository
```
git clone https://github.com/visheshrwl/osi_model
cd osi_model
```

2. Build the Project
```
cargo build
```

3. Run the Tests:
```
cargo test
```

## Project Structure

```
osi_model/
├── src/
│   ├── application.rs
│   ├── presentation.rs
│   ├── session.rs
│   ├── transport.rs
│   ├── network.rs
│   ├── datalink.rs
│   └── physical.rs
├── tests/
│   ├── application_tests.rs
│   ├── presentation_tests.rs
│   ├── session_tests.rs
│   ├── transport_tests.rs
│   ├── network_tests.rs
│   ├── datalink_tests.rs
│   └── physical_tests.rs
├── Cargo.toml
└── README.md
```

## Usage
### Running the Application
To run the main application, use the following command:
```
cargo run
```

This command will execute the main function defined in `src/main.rs`, demonstrating the interaction between the different OSI layers.

### Examples
Here is an example of how to initiate a session, send data, and terminate the session:
```
fn main() {
    session::initiate_session("192.168.1.1:8000");
    let data = "Hello, world";
    let encrypted_data = presentation::encrypt(data.as_bytes());
    let compressed_data = presentation::compress(&encrypted_data);
    let segment = transport::tcp::send_segment(&compressed_data, "192.168.1.1:8000");
    let packet = network::create_packet(&segment, "192.168.1.1");
    datalink::create_frame(&packet);
    session::terminate_session();
}
```


## Contributing

We welcome contributioons to enhance this project. Please follow these steps:

**1.** Fork the repository.

**2.** Clone your forked copy of the project. 

```

git clone https://github.com/<your_name>/osi_model.git 

```

**3.** Navigate to the project directory.

```

cd osi_model

```

**4.** Add a reference(remote) to the original repository. 
```
git remote add upstream https://github.com/visheshrwl/osi_model
```

**5.** Check the remotes for this repository.
```
git remote -v
```

**6.** Always take a pull from the upstream repository to your master branch to keep it at par with the main project(updated repository). 
```
git pull upstream main
```

**7.** Create a new branch. 
```
git checkout -n <your_branch_name>
```

**8.** Perform your desired changes to the code base on that branch.

**9.** Track your changes. 
```
git add .
```

**10.** Commit your changes. 
```
git commit -m "Relevant message"
```

**11.** Push the committed changes in your feature branch to your remote repo. 
```
git push -u origin <your_branch_name>
```

**12.** To create a pull request, click on `compare and pull requests. Please ensure you compare your feature branch to the desired branch of the repository you are supposed to make a PR to.

**13.** Add an appropriate title and description to your pull request explaining your changes and efforts.

**14.** Click on `Create Pull Request.`

**15.** Voila! You have made a PR to Bug Buster's Community Website. Sit back patiently and relax while your PR is reviewed.

<h2 align="center"> Project Maintainers & Admins</h2>
<div align="center">
    <a href="https://github.com/visheshrwl">
    <img src="https://avatars.githubusercontent.com/u/92795514?v=4" width=100px height=100px />
    </a>
    <p align="center">Vishesh Rawal</p>
</div>

<h2 align="center"> Project Contributors </h2>

<div align="center">
<a href="https://github.com/visheshrwl/osi_model/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=visheshrwl/osi_model" />
</a>
</div>