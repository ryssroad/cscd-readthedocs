# Voting Power Calculation

Voting power in bCC contracts is calculated based on a user's past and current interactions. \
The `_bias` variable in our contract code represents the voting power of a user during their last interaction.

{% code overflow="wrap" %}
```python
_epoch: uint256 = self.user_point_epoch[addr]
last_point: Point = self.user_point_history[addr][_epoch]
_bias: int128 = last_point.bias

return _bias
```
{% endcode %}

To derive the current voting power, we use:

{% code overflow="wrap" %}
```python
_bias -= last_point.slope * convert(_t - last_point.ts, int128)
```
{% endcode %}

In essence, `userVP = last_interaction_VP - interaction_slope * (current_timestamp - last_interaction_timestamp)`. Slope and bias calculations occur within the `_checkpoint()` function, which is called when:

1. A lock is created.
2. A lock amount increases.
3. A cooldown starts.
4. A cooldown gets renewed.
5. A lock gets withdrawn.
