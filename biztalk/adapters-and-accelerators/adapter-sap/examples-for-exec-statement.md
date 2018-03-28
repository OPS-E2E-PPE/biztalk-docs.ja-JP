---
title: EXEC ステートメントの例は、BizTalk での mySAP アダプターで |Microsoft ドキュメント
description: EXEC 例と、mySAP アダプターの BizTalk アダプター パック (BAP) を使用するサンプル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eaae930d7d94d24bac9d484957ccf02718af60f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="examples-for-exec-statement"></a>EXEC ステートメントの例
このトピックでは、さまざまな EXEC ステートメントの構文例を示します。

## <a name="sample-statements"></a>ステートメントの例 
  
-   入力パラメーターをとらない BAPI を実行するには次の構文を使用します。データがによって返される、 **DataReader**オブジェクト。  
  
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
  
     この例では、という名前のパラメーターを作成する必要があります`@var`RFC_CUSTOMER_GET の最初のパラメーターが KUNNR (カスタマー番号) に対応しているために、(たとえばを 1001 に)、値を明示的に設定し、  
  
-   入力パラメーター名の変数を使用する RFC を実行するには、次の構文を使用します。  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     という名前のパラメーターを作成する必要があります`@var1`の値を指定、および対応するコマンド オブジェクトにバインドします。 新しく作成されたパラメーター オブジェクトの既定の方向は`input`します。  
  
-   BAPI と戻り値のテーブルをパラメーターとして、実行するには、次の構文を使用します。  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     という名前のパラメーターを作成する必要があります`@var1`の値を指定し、対応するコマンド オブジェクトにバインドします。 新しく作成されたパラメーター オブジェクトの方向にする必要があります`InputOutput`または`Output`です。  
  
-   次の EXEC 例では、テーブルの複合型パラメーターを使用します。 例では、@fieldsテーブル パラメーターです。  
  
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
  
-   EXEC の次の例では、構造体の複合型を使用します。 例では、@equimaster構造体のパラメーターです。  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a>複雑なパラメーターの型のサポート  
 複合の RFC パラメーター (テーブルと構造体) をサポートするために 2 つの方法を使用する場合、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  
  
-   複合型のインライン XML 値を提供します。 この例は、複雑なパラメーターの型に XML を渡す方法を示しています。*フィールド*です。 次の例では、 *@fields*テーブル パラメーターです。  
  
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
  
-   作成、 **DataTable**複合型および SAP パラメーターの値をセット内のフィールドの列を含むパラメーター **DataTable**です。 この例は、設定する方法を示します、@fields複合型を使用して、 **DataTable**です。  
  
    ```  
    cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
    DataTable dt = new DataTable();  
    dt.Columns.Add("FIELDNAME");  
    SAPParameter p = new SAPParameter("@p_fields");  
    p.Value = dt;  
    ```  
  
## <a name="limitations"></a>制限事項  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]複合型の次の制限があります。  
  
-   渡す場合、複合型のパラメーターを使用して、 **DataTable**での複合型のすべてのフィールド (列) を含める必要があります、 **DataTable**です。  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]はサポートしていません**DbNull**です。 設定することはできません**DbNull**のパラメーターの値として。  
  
