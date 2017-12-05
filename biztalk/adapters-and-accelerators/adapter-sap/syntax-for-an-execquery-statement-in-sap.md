---
title: "SAP 内の EXECQUERY ステートメントに対して構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5198335cfa1a7d2036ca05759edc7d04e28cc20b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a>SAP の EXECQUERY ステートメントの構文
SAP の GUI を使用すると、グラフィカルに表示するクエリ、列および並べ替え順序など、結果セットに含めるテーブルを選択してクエリを作成します。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET アプリケーションからユーザーは、SAP システムで定義されているクエリの実行に使用できる EXECQUERY 操作を提供することによってこのようなクエリを実行することができます。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム RFC Z_EXECUTE_SAP_QUERY を使用して、SAP システムで定義済みのクエリを実行します。 カスタムの RFC には、これは、標準の SAP システムで定義されている RFC、RSAQ_REMOTE_QUERY_CALL さらに実行します。 そのため、EXECQUERY 操作を使用することができます、前に、に対するクエリを実行して、SAP システムでカスタム RFC をインストールする必要があります。 カスタムの RFC をインストールする方法の手順については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。  
  
 このトピックでは、EXECQUERY 操作および EXECQUERY 操作に関連するその他の有用な情報の構文について説明します。  
  
## <a name="syntax-for-an-execquery-statement"></a>EXECQUERY ステートメントの構文  
 次のセクションでは、に対して EXECQUERY 操作を使用するための文法仕様をについて説明します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 それぞれの文字の説明は次のとおりです。  
  
-   **\<QueryName\>**  SAP システムで定義されたクエリの名前を指定します。  
  
-   **USERGROUP**クエリが定義されているユーザー グループを参照します。 これは、必須のパラメーターです。  
  
-   **ワークスペース**クエリが定義されているワークスペースを参照します。 、SAP では、2 つのワークスペースは、Standard、およびグローバルです。 標準のワークスペースを指定する空の領域を提供します。 提供`X`グローバル ワークスペースを指定します。 既定値は、空の領域です。  
  
-   **VARIANT**保存されている SAP クエリの実行中に指定できる選択条件のセットを指します。 たとえば、バリアントを使用すると、クエリの既定値を指定します。  
  
-   **@Pn**n を指す<sup>th</sup> SAP クエリの定義でフィールドを選択します。  
  
-   **USEORIGINALCOLUMNNAMES** SAP システム内に存在すると、プロバイダーが、データセットで元の列名を使用するかどうかを指定します。 既定では、プロバイダーは、SAP クエリで定義されているフレンドリ名を使用します。 ただし、クエリ内でのわかりやすい名前が一意でない場合、ADO.NET クライアントはエラーをスロー、データセットからデータを読み取り中にします。 このようなシナリオである必要がありますオプションを指定する、USEORIGINALCOLUMNNAMES プロバイダーがデータセットの元の列名を使用することを示すです。  
  
    > [!IMPORTANT]
    >  たとえば、常に 1 つの引用符で囲まれたオプションのキーワードの値を指定する必要があります '*USEORIGINALCOLUMNNAMES*' です。  
  
> [!NOTE]
>  SAP クエリのパラメーターが EXECQUERY 構文に変換する方法については、次を参照してください。 [EXECQUERY コマンドにクエリ パラメーターの変換の SAP](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)です。  
  
### <a name="framing-an-execquery-syntax"></a>EXECQUERY 構文のフレーム化  
 SAP クエリの実行に EXECQUERY 操作の構文のフレームは、SAP で定義されている各パラメーターの値を含む、SAP システムでクエリを定義する方法によって異なります。 SAP クエリの実行に EXECQUERY 構文のフレームをする方法については、次を参照してください。 [EXECQUERY コマンドにクエリ パラメーターの変換の SAP](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)です。  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a>追加の考慮事項中に操作を使用して、EXECQUERY  
 このセクションでは、EXECQUERY ステートメントを使用する場合は、点に注意する必要がありますポイントを一覧表示[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
-   として USERGROUP、ワークスペース、およびバリアント型の指定した値を渡すには標準の SAP RFC RSAQ_REMOTE_QUERY_CALL をします。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこれらのパラメーターの指定した値は検証されません。  
  
-   EXECQUERY 操作によって返されるすべての値では、文字列型です。  
  
-   クエリ名、ユーザー グループ、ワークスペース、およびバリアントのキーワードは、大文字と小文字が区別されません。 ただし、パラメーター名は常にある上位 caseP でなど@P1、 @P2, などです。例:  
  
    ```  
    EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
     同じです。  
  
    ```  
    EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
-   EXECQUERY でサポートされている演算子は、>、<>、=、< =、! =、NOT、および BETWEEN です。  
  
-   EXECQUERY 操作によっては、ワイルドカード文字はサポートされていません。 たとえば、次のステートメントが予想される出力。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
     ただし、ワイルドカード文字を使用して実行する際、同じクエリでは、エラーを示します。 ワイルドカード文字の使用に注意してください **@P2**です。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
    ```  
  
     この例では、データが見つからなかったことを示すエラーを取得可能性があります。 これは、クエリを検索するため**'\*&\*'**を文字列としてし、ワイルドカード文字としてアスタリスク (*) を考慮しません。  
  
-   必ず、YYYYMMDD の形式で日付値を指定する必要があります。  
  
-   SAP システムで定義されているバリエーションがあるクエリを実行している場合は、コマンドの一部として、バリアント型の名前を指定できます。 例:  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
    ```  
  
    > [!NOTE]
    >  SAP システムでクエリの既定のバリエーションが定義されている場合は、バリアントの名前を指定する必要はありません。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)