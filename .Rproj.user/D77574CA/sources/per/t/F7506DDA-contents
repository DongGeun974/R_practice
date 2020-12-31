library(shiny)
library(shiny)

myFunc <- function(x, y){
  return(x+y)
}


ui <- fluidPage(
  textInput("txt1",
            label = h3("input value 1"),
            value = "var1"
  ),
  textInput("txt2",
            label = h3("input value 2"),
            value = "var2"
  ),
  
  actionButton('btn1', 'ButtonLabel'),

  hr(),
  
  textOutput("var"),
  textOutput("res")
)


server <- function(input, output, session) {
  
  observeEvent(input$btn1, {
    val1 <- {input$txt1}
    val2 <- {input$txt2}
    
    str = paste("value 1 = ", as.character(val1), ",", 
                "value 2 = ", as.character(val2))
    res = myFunc(as.numeric(val1), as.numeric(val2))
    
    output$var = renderText(str)
    output$res = renderText(res)
  })
  
}


shinyApp(ui, server)