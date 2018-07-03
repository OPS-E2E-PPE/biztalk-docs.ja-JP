---
title: SAP に EXECQUERY ステートメントの構文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf479438a5b0960a66b35ef7946df63d088284b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982019"
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a>SAP に EXECQUERY ステートメントの構文
SAP GUI を使用すると、グラフィカルに表示するクエリ、列および並べ替え順序など、結果セットに含めるテーブルを選択してクエリを作成します。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET アプリケーションからユーザーが SAP システムで定義されているクエリの実行に使用できる EXECQUERY 操作を提供することでこのようなクエリを実行することができます。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム RFC Z_EXECUTE_SAP_QUERY を使用して、SAP システムで定義済みのクエリを実行します。 カスタム RFC には、これは、標準の SAP システムで定義されている RFC、RSAQ_REMOTE_QUERY_CALL さらに実行します。 そのため、EXECQUERY 操作を使用する前に、に対するクエリを実行する SAP システムでカスタム RFC をインストールする必要があります。 カスタム RFC をインストールする方法の手順については、次を参照してください。 [Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。  
  
 このトピックでは、EXECQUERY 操作、および EXECQUERY 操作に関連するその他の有用な情報の構文について説明します。  
  
## <a name="syntax-for-an-execquery-statement"></a>EXECQUERY ステートメントの構文  
 次のセクションの説明に対する EXECQUERY 操作を使用して文法の仕様、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 それぞれの文字の説明は次のとおりです。  
  
- **\<QueryName\>**  SAP システムで定義されているクエリの名前を指定します。  
  
- **USERGROUP**は、クエリが定義されているユーザー グループを指します。 これは、必須パラメーターです。  
  
- **ワークスペース**クエリが定義されているワークスペースを参照します。 Sap では、2 つのワークスペース: Standard、およびグローバルです。 Standard ワークスペースを指定する空の領域を提供します。 提供`X`グローバルのワークスペースを指定します。 既定値は、空の領域です。  
  
- **VARIANT**と SAP クエリの実行中に指定できる選択条件の保存されているセットを指します。 たとえば、バリアントを使用すると、クエリの既定値を指定します。  
  
- <strong>@Pn</strong> n を指す<sup>th</sup> SAP クエリの定義でフィールドを選択します。  
  
- **USEORIGINALCOLUMNNAMES** SAP システム内に存在するプロバイダーは、データセットの元の列名を使用するかどうかを指定します。 既定では、プロバイダーは、SAP クエリで定義されているフレンドリ名を使用します。 ただし、そのクエリ内での表示名が一意でない場合、ADO.NET クライアントは、データセットからデータを読み取り中にエラーをスローします。 このようなシナリオでする必要がありますオプションを指定する USEORIGINALCOLUMNNAMES、プロバイダーがデータセットの元の列名を使用することを示します。  
  
  > [!IMPORTANT]
  >  たとえば、常に単一引用符で囲まれたオプションのキーワードの値を指定する必要があります '*USEORIGINALCOLUMNNAMES*'。  
  
> [!NOTE]
>  SAP クエリのパラメーターを EXECQUERY 構文に変換する方法については、次を参照してください。[変換 SAP クエリのパラメーターを EXECQUERY コマンドに](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)します。  
  
### <a name="framing-an-execquery-syntax"></a>フレーム、EXECQUERY 構文  
 SAP クエリを実行するための EXECQUERY 操作の構文のフレーム化は、SAP で定義されている各パラメーターの値を含む、SAP システムでクエリを定義する方法によって異なります。 フレームの EXECQUERY の構文を SAP クエリを実行する方法については、次を参照してください。[変換 SAP クエリのパラメーターを EXECQUERY コマンドに](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)します。  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a>追加の考慮事項、操作を使用して、EXECQUERY  
 このセクションに一覧表示されたポイントを指定して EXECQUERY ステートメントを使用する場合、点に注意する必要があります[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。  
  
- としてユーザー グループ、ワークスペース、およびバリアントの値を渡すには標準の SAP RFC RSAQ_REMOTE_QUERY_CALL をします。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこれらのパラメーターに指定された値は検証されません。  
  
- EXECQUERY 操作によって返されるすべての値では、文字列型です。  
  
- クエリ名、ユーザー グループ、ワークスペース、およびバリアントのキーワードは大文字小文字が区別されません。 ただし、パラメーター名は常上限 caseP など@P1、@P2など。以下に例を示します。  
  
  ```  
  EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
   同じです。  
  
  ```  
  EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
- EXECQUERY でサポートされている演算子は、>、<>、=、< =、! =、NOT、BETWEEN とします。  
  
- ワイルドカード文字は EXECQUERY 操作ではサポートされていません。 たとえば、次のステートメント、予想される出力されます。  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
  ```  
  
   ただし、ワイルドカード文字で実行されると、同じクエリでは、エラーを示します。 用のワイルドカード文字の使用に注意してください <strong>@P2</strong>します。  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
  ```  
  
   この例では、データが見つからなかったことを示すエラーを取得可能性があります。 これは、クエリを検索するため **'\*&\*'** を文字列としてされ、ワイルドカード文字としてアスタリスク (*) は考慮されません。  
  
- 常に、YYYYMMDD の形式で日付値を指定する必要があります。  
  
- SAP システムで定義されたバリアントがあるクエリを実行している場合は、コマンドの一部としてバリアントの名前を指定できます。 以下に例を示します。  
  
  ```  
  EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
  ```  
  
  > [!NOTE]
  >  SAP システムでクエリの既定のバリエーションが定義されている場合は、バリアントの名前を指定する必要はありません。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)