# DS Chat+Mongo lab

## Before

rs.status()
```json
{
	"set" : "rs0",
	"date" : ISODate("2019-11-01T07:57:12.051Z"),
	"myState" : 1,
	"term" : NumberLong(3),
	"syncingTo" : "",
	"syncSourceHost" : "",
	"syncSourceId" : -1,
	"heartbeatIntervalMillis" : NumberLong(2000),
	"majorityVoteCount" : 2,
	"writeMajorityCount" : 2,
	"optimes" : {
		"lastCommittedOpTime" : {
			"ts" : Timestamp(1572595023, 1),
			"t" : NumberLong(3)
		},
		"lastCommittedWallTime" : ISODate("2019-11-01T07:57:03.965Z"),
		"readConcernMajorityOpTime" : {
			"ts" : Timestamp(1572595023, 1),
			"t" : NumberLong(3)
		},
		"readConcernMajorityWallTime" : ISODate("2019-11-01T07:57:03.965Z"),
		"appliedOpTime" : {
			"ts" : Timestamp(1572595023, 1),
			"t" : NumberLong(3)
		},
		"durableOpTime" : {
			"ts" : Timestamp(1572595023, 1),
			"t" : NumberLong(3)
		},
		"lastAppliedWallTime" : ISODate("2019-11-01T07:57:03.965Z"),
		"lastDurableWallTime" : ISODate("2019-11-01T07:57:03.965Z")
	},
	"lastStableRecoveryTimestamp" : Timestamp(1572594973, 1),
	"lastStableCheckpointTimestamp" : Timestamp(1572594973, 1),
	"electionCandidateMetrics" : {
		"lastElectionReason" : "stepUpRequestSkipDryRun",
		"lastElectionDate" : ISODate("2019-11-01T07:54:22.624Z"),
		"termAtElection" : NumberLong(3),
		"lastCommittedOpTimeAtElection" : {
			"ts" : Timestamp(1572594855, 1),
			"t" : NumberLong(2)
		},
		"lastSeenOpTimeAtElection" : {
			"ts" : Timestamp(1572594855, 1),
			"t" : NumberLong(2)
		},
		"numVotesNeeded" : 2,
		"priorityAtElection" : 1,
		"electionTimeoutMillis" : NumberLong(10000),
		"priorPrimaryMemberId" : 0,
		"numCatchUpOps" : NumberLong(27017),
		"newTermStartDate" : ISODate("2019-11-01T07:54:23.960Z"),
		"wMajorityWriteAvailabilityDate" : ISODate("2019-11-01T07:54:25.172Z")
	},
	"members" : [
		{
			"_id" : 0,
			"name" : "172.31.37.153:27017",
			"ip" : "172.31.37.153",
			"health" : 1,
			"state" : 2,
			"stateStr" : "SECONDARY",
			"uptime" : 166,
			"optime" : {
				"ts" : Timestamp(1572595023, 1),
				"t" : NumberLong(3)
			},
			"optimeDurable" : {
				"ts" : Timestamp(1572595023, 1),
				"t" : NumberLong(3)
			},
			"optimeDate" : ISODate("2019-11-01T07:57:03Z"),
			"optimeDurableDate" : ISODate("2019-11-01T07:57:03Z"),
			"lastHeartbeat" : ISODate("2019-11-01T07:57:11.293Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T07:57:11.648Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "",
			"syncingTo" : "172.31.20.194:27017",
			"syncSourceHost" : "172.31.20.194:27017",
			"syncSourceId" : 1,
			"infoMessage" : "",
			"configVersion" : 3
		},
		{
			"_id" : 1,
			"name" : "172.31.20.194:27017",
			"ip" : "172.31.20.194",
			"health" : 1,
			"state" : 1,
			"stateStr" : "PRIMARY",
			"uptime" : 235,
			"optime" : {
				"ts" : Timestamp(1572595023, 1),
				"t" : NumberLong(3)
			},
			"optimeDate" : ISODate("2019-11-01T07:57:03Z"),
			"syncingTo" : "",
			"syncSourceHost" : "",
			"syncSourceId" : -1,
			"infoMessage" : "",
			"electionTime" : Timestamp(1572594862, 1),
			"electionDate" : ISODate("2019-11-01T07:54:22Z"),
			"configVersion" : 3,
			"self" : true,
			"lastHeartbeatMessage" : ""
		},
		{
			"_id" : 2,
			"name" : "172.31.34.92:27017",
			"ip" : "172.31.34.92",
			"health" : 1,
			"state" : 2,
			"stateStr" : "SECONDARY",
			"uptime" : 233,
			"optime" : {
				"ts" : Timestamp(1572595023, 1),
				"t" : NumberLong(3)
			},
			"optimeDurable" : {
				"ts" : Timestamp(1572595023, 1),
				"t" : NumberLong(3)
			},
			"optimeDate" : ISODate("2019-11-01T07:57:03Z"),
			"optimeDurableDate" : ISODate("2019-11-01T07:57:03Z"),
			"lastHeartbeat" : ISODate("2019-11-01T07:57:10.714Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T07:57:11.251Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "",
			"syncingTo" : "172.31.20.194:27017",
			"syncSourceHost" : "172.31.20.194:27017",
			"syncSourceId" : 1,
			"infoMessage" : "",
			"configVersion" : 3
		}
	],
	"ok" : 1,
	"$clusterTime" : {
		"clusterTime" : Timestamp(1572595023, 1),
		"signature" : {
			"hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),
			"keyId" : NumberLong(0)
		}
	},
	"operationTime" : Timestamp(1572595023, 1)
}
```

rs.config()
```json
{
	"_id" : "rs0",
	"version" : 3,
	"protocolVersion" : NumberLong(1),
	"writeConcernMajorityJournalDefault" : true,
	"members" : [
		{
			"_id" : 0,
			"host" : "172.31.37.153:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {

			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 1,
			"host" : "172.31.20.194:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {

			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 2,
			"host" : "172.31.34.92:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {

			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		}
	],
	"settings" : {
		"chainingAllowed" : true,
		"heartbeatIntervalMillis" : 2000,
		"heartbeatTimeoutSecs" : 10,
		"electionTimeoutMillis" : 10000,
		"catchUpTimeoutMillis" : -1,
		"catchUpTakeoverDelayMillis" : 30000,
		"getLastErrorModes" : {

		},
		"getLastErrorDefaults" : {
			"w" : 1,
			"wtimeout" : 0
		},
		"replicaSetId" : ObjectId("5dbbddc58d72934a854aaa83")
	}
}
```


## After

rs.status()
```json
{
	"set" : "rs0",
	"date" : ISODate("2019-11-01T08:03:34.436Z"),
	"myState" : 1,
	"term" : NumberLong(5),
	"syncingTo" : "",
	"syncSourceHost" : "",
	"syncSourceId" : -1,
	"heartbeatIntervalMillis" : NumberLong(2000),
	"majorityVoteCount" : 2,
	"writeMajorityCount" : 2,
	"optimes" : {
		"lastCommittedOpTime" : {
			"ts" : Timestamp(1572595408, 1),
			"t" : NumberLong(5)
		},
		"lastCommittedWallTime" : ISODate("2019-11-01T08:03:28.896Z"),
		"readConcernMajorityOpTime" : {
			"ts" : Timestamp(1572595408, 1),
			"t" : NumberLong(5)
		},
		"readConcernMajorityWallTime" : ISODate("2019-11-01T08:03:28.896Z"),
		"appliedOpTime" : {
			"ts" : Timestamp(1572595408, 1),
			"t" : NumberLong(5)
		},
		"durableOpTime" : {
			"ts" : Timestamp(1572595408, 1),
			"t" : NumberLong(5)
		},
		"lastAppliedWallTime" : ISODate("2019-11-01T08:03:28.896Z"),
		"lastDurableWallTime" : ISODate("2019-11-01T08:03:28.896Z")
	},
	"lastStableRecoveryTimestamp" : Timestamp(1572595378, 1),
	"lastStableCheckpointTimestamp" : Timestamp(1572595378, 1),
	"electionCandidateMetrics" : {
		"lastElectionReason" : "stepUpRequestSkipDryRun",
		"lastElectionDate" : ISODate("2019-11-01T08:02:47.901Z"),
		"termAtElection" : NumberLong(5),
		"lastCommittedOpTimeAtElection" : {
			"ts" : Timestamp(1572595366, 1),
			"t" : NumberLong(4)
		},
		"lastSeenOpTimeAtElection" : {
			"ts" : Timestamp(1572595366, 1),
			"t" : NumberLong(4)
		},
		"numVotesNeeded" : 2,
		"priorityAtElection" : 1,
		"electionTimeoutMillis" : NumberLong(10000),
		"priorPrimaryMemberId" : 0,
		"numCatchUpOps" : NumberLong(27017),
		"newTermStartDate" : ISODate("2019-11-01T08:02:48.894Z"),
		"wMajorityWriteAvailabilityDate" : ISODate("2019-11-01T08:02:49.766Z")
	},
	"members" : [
		{
			"_id" : 0,
			"name" : "172.31.37.153:27017",
			"ip" : "172.31.37.153",
			"health" : 0,
			"state" : 8,
			"stateStr" : "(not reachable/healthy)",
			"uptime" : 0,
			"optime" : {
				"ts" : Timestamp(0, 0),
				"t" : NumberLong(-1)
			},
			"optimeDurable" : {
				"ts" : Timestamp(0, 0),
				"t" : NumberLong(-1)
			},
			"optimeDate" : ISODate("1970-01-01T00:00:00Z"),
			"optimeDurableDate" : ISODate("1970-01-01T00:00:00Z"),
			"lastHeartbeat" : ISODate("2019-11-01T08:03:33.957Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T08:02:46.970Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "Error connecting to 172.31.37.153:27017 :: caused by :: Connection refused",
			"syncingTo" : "",
			"syncSourceHost" : "",
			"syncSourceId" : -1,
			"infoMessage" : "",
			"configVersion" : -1
		},
		{
			"_id" : 1,
			"name" : "172.31.20.194:27017",
			"ip" : "172.31.20.194",
			"health" : 1,
			"state" : 1,
			"stateStr" : "PRIMARY",
			"uptime" : 88,
			"optime" : {
				"ts" : Timestamp(1572595408, 1),
				"t" : NumberLong(5)
			},
			"optimeDate" : ISODate("2019-11-01T08:03:28Z"),
			"syncingTo" : "",
			"syncSourceHost" : "",
			"syncSourceId" : -1,
			"infoMessage" : "",
			"electionTime" : Timestamp(1572595367, 1),
			"electionDate" : ISODate("2019-11-01T08:02:47Z"),
			"configVersion" : 3,
			"self" : true,
			"lastHeartbeatMessage" : ""
		},
		{
			"_id" : 2,
			"name" : "172.31.34.92:27017",
			"ip" : "172.31.34.92",
			"health" : 1,
			"state" : 2,
			"stateStr" : "SECONDARY",
			"uptime" : 87,
			"optime" : {
				"ts" : Timestamp(1572595408, 1),
				"t" : NumberLong(5)
			},
			"optimeDurable" : {
				"ts" : Timestamp(1572595408, 1),
				"t" : NumberLong(5)
			},
			"optimeDate" : ISODate("2019-11-01T08:03:28Z"),
			"optimeDurableDate" : ISODate("2019-11-01T08:03:28Z"),
			"lastHeartbeat" : ISODate("2019-11-01T08:03:33.927Z"),
			"lastHeartbeatRecv" : ISODate("2019-11-01T08:03:33.787Z"),
			"pingMs" : NumberLong(0),
			"lastHeartbeatMessage" : "",
			"syncingTo" : "172.31.20.194:27017",
			"syncSourceHost" : "172.31.20.194:27017",
			"syncSourceId" : 1,
			"infoMessage" : "",
			"configVersion" : 3
		}
	],
	"ok" : 1,
	"$clusterTime" : {
		"clusterTime" : Timestamp(1572595408, 1),
		"signature" : {
			"hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),
			"keyId" : NumberLong(0)
		}
	},
	"operationTime" : Timestamp(1572595408, 1)
}
```

rs.config()
```json
{
	"_id" : "rs0",
	"version" : 3,
	"protocolVersion" : NumberLong(1),
	"writeConcernMajorityJournalDefault" : true,
	"members" : [
		{
			"_id" : 0,
			"host" : "172.31.37.153:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {

			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 1,
			"host" : "172.31.20.194:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {

			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		},
		{
			"_id" : 2,
			"host" : "172.31.34.92:27017",
			"arbiterOnly" : false,
			"buildIndexes" : true,
			"hidden" : false,
			"priority" : 1,
			"tags" : {

			},
			"slaveDelay" : NumberLong(0),
			"votes" : 1
		}
	],
	"settings" : {
		"chainingAllowed" : true,
		"heartbeatIntervalMillis" : 2000,
		"heartbeatTimeoutSecs" : 10,
		"electionTimeoutMillis" : 10000,
		"catchUpTimeoutMillis" : -1,
		"catchUpTakeoverDelayMillis" : 30000,
		"getLastErrorModes" : {

		},
		"getLastErrorDefaults" : {
			"w" : 1,
			"wtimeout" : 0
		},
		"replicaSetId" : ObjectId("5dbbddc58d72934a854aaa83")
	}
}
```

Screens are in 'screens' folder

Reference: https://dev.to/rexeze/how-to-build-a-real-time-chat-app-with-nodejs-socketio-and-mongodb-2khohttps://dev.to/rexeze/how-to-build-a-real-time-chat-app-with-nodejs-socketio-and-mongodb-2kho