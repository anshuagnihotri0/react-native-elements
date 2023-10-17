import React, { Component } from 'react';
import { View, Text, Button, CheckBox } from 'react-native';
import { Card, ListItem } from 'react-native-elements';

class VotingPage extends Component {
  constructor(props) {
    super(props);
    this.state = {
      candidates: [
        { name: 'Candidate A', votes: 0 },
        { name: 'Candidate B', votes: 0 },
        // Add more candidates as needed
      ],
      selectedCandidate: null,
    };
  }

  handleVote = () => {
    const { selectedCandidate, candidates } = this.state;
    if (selectedCandidate !== null) {
      candidates[selectedCandidate].votes += 1;
      this.setState({ candidates });
    }
  };

  render() {
    return (
      <View>
        <Text style={{ fontSize: 24, textAlign: 'center' }}>Online Voting System</Text>
        <Card>
          <Text>Choose your candidate:</Text>
          {this.state.candidates.map((candidate, index) => (
            <ListItem
              key={index}
              title={candidate.name}
              rightElement={
                <CheckBox
                  checked={this.state.selectedCandidate === index}
                  onPress={() => this.setState({ selectedCandidate: index })}
                />
              }
            />
          ))}
        </Card>
        <Button title="Vote" onPress={this.handleVote} />
        <Card>
          <Text>Vote Results:</Text>
          {this.state.candidates.map((candidate, index) => (
            <Text key={index}>
              {candidate.name}: {candidate.votes} votes
            </Text>
          ))}
        </Card>
      </View>
    );
  }
}

export default VotingPage;
