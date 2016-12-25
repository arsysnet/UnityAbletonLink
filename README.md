# UnityAbletonLink

UnityAbletonLink is an [Ableton Link](https://github.com/Ableton/link) plugin for [Unity](https://unity3d.com).

## Building

After checked out the UnityAbletonLink repository, then check out all dependencies.

```
cd UnityAbletonLink
git submodule update --init --recursive
```

Open `UnityAbletonLink.xcodeproj` with Xcode, then build it.

## Running

Create a project in Unity and create a `plugin` folder in it.

Copy `UnityAbletonLink.bundle` and `CSharp/AbletonLink.cs` into the `plugin` folder.

Where `AbletonLink.cs` is a wrapper script for `UnityAbletonLink` plugin.

Write some script to use it.
For example,

```Example.cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Example : MonoBehaviour {

	private AbletonLink link;

	// Use this for initialization
	void Start () {
	}

	// Update is called once per frame
	void Update () {
		double beat, phase;
		AbletonLink.Instance.update (out beat, out phase);
    // We can obtain the latest beat and phase like this.
		Debug.Log ("beat: " + beat + " phase:" + phase);
	}
}
```
