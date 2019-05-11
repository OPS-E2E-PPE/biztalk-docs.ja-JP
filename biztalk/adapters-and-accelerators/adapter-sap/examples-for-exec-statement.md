---
title: BizTalk での mySAP アダプターの EXEC ステートメントの例 |Microsoft Docs
description: EXEC 例と、mySAP アダプターを BizTalk アダプター パック (BAP) を使用したサンプル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75345610fe1585fa5af14f7202d7f87613629198
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373469"
---
# <a name="examples-for-exec-statement"></a>EXEC ステートメントの例
このトピックでは、さまざまな EXEC ステートメントの構文の例を示します。

## <a name="sample-statements"></a>サンプル ステートメント 
  
-   入力パラメーターをとらない BAPI を実行するには、次の構文を使用して、データがによって返される、 **DataReader**オブジェクト。  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   入力パラメーターを受け取る RFC を実行するには、次の構文を使用します。  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   変数として指定された入力パラメーターを受け取る RFC を実行するには、次の構文を使用します。  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     この例では、という名前のパラメーターを作成する必要があります`@var`し RFC_CUSTOMER_GET の最初のパラメーターが KUNNR (カスタマー番号) に対応しているため (たとえば、1001) を明示的に値を設定  
  
-   入力パラメーター名の変数を使用する RFC を実行するには、次の構文を使用します。  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     という名前のパラメーターを作成する必要があります`@var1`の値を指定し、対応するコマンド オブジェクトにバインドします。 新しく作成されたパラメーター オブジェクトの既定の方向は`input`します。  
  
-   BAPI と戻り値のテーブルをパラメーターとしてを実行するには、次の構文を使用します。  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     という名前のパラメーターを作成する必要があります`@var1`で、値を指定して、対応するコマンド オブジェクトにバインドします。 新しく作成されたパラメーター オブジェクトの方向にする必要があります`InputOutput`または`Output`します。  
  
-   次の EXEC の例では、テーブルの複合型パラメーターを使用します。 例では、@fieldsテーブル パラメーターです。  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   次の EXEC の例では、構造体の複合型を使用します。 例では、@equimaster構造体のパラメーターです。  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a>複雑なパラメーターの型のサポート  
 複雑な RFC パラメーター (テーブルと構造体) をサポートするために 2 つの方法を使用すると、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  
  
- 複合型のインライン XML 値を提供します。 この例では、複雑なパラメーターの型に XML を渡す*フィールド*します。 次の例では、 <em>@fields</em>テーブル パラメーターです。  
  
  ```  
  exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
              <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                <FIELDNAME>BANKL</FIELDNAME>  
              </RFC_DB_FLD>  
              <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKS</FIELDNAME>  
              </RFC_DB_FLD>  
            </FIELDS>', @fields=@flds output  
  ```  
  
- 作成、 **DataTable**複合型および SAP パラメーターの値をセット内のフィールドの列を持つパラメーター **DataTable**します。 この例では、設定、@fields複合型を使用して、 **DataTable**します。  
  
  ```  
  cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
  DataTable dt = new DataTable();  
  dt.Columns.Add("FIELDNAME");  
  SAPParameter p = new SAPParameter("@p_fields");  
  p.Value = dt;  
  ```  
  
## <a name="limitations"></a>制限事項  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]複合型の場合、次の制限があります。  
  
- 渡すと、複合型パラメーターを使用して、 **DataTable**、複合型のすべてのフィールド (列) を含める必要があります、 **DataTable**します。  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]はサポートしていません**DbNull**します。 設定することはできません**DbNull**パラメーターの値として。  
  
