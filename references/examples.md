# Examples

## Example 1: New Person With Matter Link

Input:

`记一下这个人，某合作方的商务负责人，今天在展会上聊了合作。`

Expected result:

- operation: `新建`
- fact: 在展会上聊了合作
- linked matter: current project
- task handoff: `否`

## Example 2: Existing Person With Follow-up

Input:

`张总说等下周再继续。`

Expected result:

- operation: `追加`
- fact: 对方口述下周继续 `(对方口述, 未验证)`
- task handoff: suspend or follow-up task

## Example 3: Unsupported High-Risk Label

Input:

`这个人就是典型骗子，先按高风险人物记。`

Expected result:

- operation: `待确认` or reject formal storage
- no confirmed fact written
- active confirmation required

## Example 4: Recall Instead of New Intake

Input:

`XXX 是谁来着？我下午要见他。`

Expected result:

- do recall first
- do not default to new intake
- return recent interaction and linked matters if an existing node is found

## Example 5: Weak Input

Input:

`这个人先记着。`

Expected result:

- operation: `候选` or `待追问`
- ask one minimal question instead of creating a formal node

## Example 6: Multi-Person Input

Input:

`今天在活动上见了三个人：一个商务、一个制作人、还有一个投资人。`

Expected result:

- split the people first
- do not create one merged node
- handle each person candidate separately
