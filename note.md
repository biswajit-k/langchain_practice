```python
chain = prompt | llm    # chain = llm.invoke(prompt)

chain = (
    {"context": retriever, "input": RunnablePassthrough()} 
    | prompt
    | llm
    | outputParser()
)
```


In above,
`prompt = """you are a task answering agent.
take the context as {context}.
now answer the question {input}`

`RunnablePassthrough()` will take and pass the input as it is
i.e `runnablePassthrough(input): return input`


now we can call - `chain.invoke({"input": "what is an api?"})

---