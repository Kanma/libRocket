# List the header files
set(HEADERS ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/Clipboard.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/Controls.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/DataFormatter.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/DataQuery.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/DataSource.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/DataSourceListener.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementDataGrid.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementDataGridCell.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementDataGridExpandButton.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementDataGridRow.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementForm.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementFormControl.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementFormControlDataSelect.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementFormControlInput.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementFormControlSelect.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementFormControlTextArea.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/ElementTabSet.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/Header.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Controls/SelectOption.h
)

# List the source files
set(SRCS ${LIBROCKET_SOURCE_DIR}/Source/Controls/Clipboard.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/Controls.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/DataFormatter.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/DataQuery.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/DataSource.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/DataSourceListener.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementDataGrid.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementDataGridCell.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementDataGridExpandButton.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementDataGridRow.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementForm.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementFormControl.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementFormControlDataSelect.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementFormControlInput.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementFormControlSelect.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementFormControlTextArea.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementTabSet.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementTextSelection.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/ElementTextSelection.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputType.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputType.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeButton.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeButton.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeCheckbox.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeCheckbox.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeRadio.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeRadio.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeRange.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeRange.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeSubmit.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeSubmit.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeText.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/InputTypeText.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/SelectOption.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetDropDown.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetDropDown.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetSlider.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetSlider.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetSliderInput.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetSliderInput.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInput.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInput.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInputMultiLine.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInputMultiLine.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInputSingleLine.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInputSingleLine.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInputSingleLinePassword.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/WidgetTextInputSingleLinePassword.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/XMLNodeHandlerDataGrid.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/XMLNodeHandlerDataGrid.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/XMLNodeHandlerTabSet.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/XMLNodeHandlerTabSet.h
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/XMLNodeHandlerTextArea.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Controls/XMLNodeHandlerTextArea.h
)

# List the include paths
set(INCLUDE_PATHS "${LIBROCKET_SOURCE_DIR}/Include")

include_directories(${INCLUDE_PATHS})

# Declaration of the library
xmake_create_dynamic_library(ROCKETCONTROLS RocketControls "1.2.2" "1.2.2" ${HEADERS} ${SRCS})

xmake_add_to_list_property(ROCKETCONTROLS COMPILE_DEFINITIONS "RocketControls_EXPORTS")

xmake_project_link(ROCKETCONTROLS ROCKETCORE)

# Exportations
xmake_export_include_paths(ROCKETCONTROLS ${INCLUDE_PATHS})
