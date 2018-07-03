---
title: Data Provider for SAP に関する問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f481a5f71ea5677165390177eb809239961eb9e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018437"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a>Data Provider for SAP に関する問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。  
  
##  <a name="BKMK_SAPUnknownParam"></a> SAP 用データ プロバイダーを使用して、不明なパラメーター エラー  
 **問題**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のエラーが発生しました。  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 **原因**  
  
 カスタム RFC、SAP システムにインストールされている Z_EXTRACT_DATA_OO が最新ではありません。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO、カスタムの RFC を使用して SAP テーブルに対する SELECT 操作を実行します。  
  
 **解決方法**  
  
 カスタム RFC を最新のバージョンに更新する必要があります。 この RFC、Z_EXTRACT_DATA_OO は、adapterpacknoversion 利用できます。 インストールおよびカスタム RFC をアンインストールする方法の詳細については、次を参照してください。 [Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。
  
##  <a name="BKMK_SAPOOM"></a> メモリ不足例外が SAP テーブルからデータを選択するときに  
 **問題**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムからデータを選択するときに、メモリ不足の例外をスローします。  
  
 **原因**  
  
 既定で、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一度に 10,000 行を取得します。 また、SAP システムから取得される行の各バッチは、メモリに格納されます。 だから  
  
- データの取得元となるテーブルに多数の行が含まれている場合、または  
  
- テーブルに大量のメモリを消費するデータ型の列が含まれている場合  
  
  によるメモリ消費量、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が大幅に増えるし、メモリ不足の例外が発生する可能性があります。  
  
  **解決方法**  
  
  SAP システムから取得される行の最大数を変更することができます。 SELECT ステートメントで 'batchsize' オプションを指定することによって行うことができます。 以下に例を示します。  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]ようになりました、一度に 1000 を超える行が取得され、そのため大量のメモリを消費しません。  
  
##  <a name="BKMK_SAPQueryExcep"></a> 日付値を持つパラメーターを取得するクエリの実行中に例外  
 **問題**  
  
 日付の値をとるパラメーターを持つ EXECQUERY コマンドを使用してクエリを実行するときに、次の例外を取得します。  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 **原因**  
  
 EXECQUERY コマンドを使用してクエリを実行するときに、YYYYMMDD の形式で日付の値を常に指定する必要があります。  
  
 **解決方法**  
  
 YYYYMMDD の形式で日付値を指定することを確認します。 以下に例を示します。  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a> EXECQUERY コマンドを使用してクエリを実行する NO_VARIANT 例外  
 **問題**  
  
 EXECQUERY コマンドを使用してクエリを実行するときに、次の例外が発生します。  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 **原因**  
  
 この例外の 2 つの考えられる原因があります。  
  
1. 実行しようとしているクエリでは、SAP システムで定義されているバリエーションがあります。 バリアントは、保存された一連の SAP クエリの実行中に指定できる選択条件を参照してください。 たとえば、バリアントを使用すると、クエリの既定値を指定します。  
  
2. どちらを実行しようとしているクエリが定義されているバリアントも渡されるパラメーターの値を受け取ります。  
  
   **解決方法**  
  
3. 1 の理由でクエリに関連付けられているバリアントの名前を指定していることを確認します。 以下に例を示します。  
  
   ```  
   EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
   ```  
  
4. 2 の理由で、クエリ コマンドを指定するときに、ダミーのパラメーターの名前と値を指定するを確認します。 たとえば、"myquery"クエリに実行する任意のパラメーターが必要としない場合、EXECQUERY コマンドとして指定する必要があります。  
  
   ```  
   EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
   ```  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)