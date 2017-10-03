---
title: "Data Provider 用 SAP に関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba61b75f95fad429c70da42479f22a32fa4e5a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a>Data Provider 用 SAP に関する問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。  
  
##  <a name="BKMK_SAPUnknownParam"></a>SAP 用データ プロバイダーを使用して不明なパラメーター エラー  
 **問題**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のエラーが発生しました。  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 **原因**  
  
 カスタム RFC、SAP システムにインストールされている Z_EXTRACT_DATA_OO が最新ではないです。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO、カスタムの RFC を使用して SAP テーブルに対する SELECT 操作を実行します。  
  
 **解決策**  
  
 カスタム RFC を最新のバージョンに更新する必要があります。 この RFC、Z_EXTRACT_DATA_OO は、adapterpacknoversion 使用できます。 インストールおよびカスタムの RFC をアンインストールする方法の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。
  
##  <a name="BKMK_SAPOOM"></a>SAP テーブルからデータを選択すると、メモリ例外外  
 **問題**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムからデータを選択するときに、メモリ不足の例外をスローします。  
  
 **原因**  
  
 既定では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一度に行数は 10,000 行を取得します。 また、SAP システムから取得された行の各バッチは、メモリに格納されます。 だから  
  
-   データの取得元となるテーブルに多数の行が含まれている場合、または  
  
-   テーブルに大量のメモリを消費するデータ型の列が含まれている場合  
  
 によるメモリ消費、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が大幅に増加し、メモリ不足の例外が発生する可能性があります。  
  
 **解決策**  
  
 SAP システムから取得された行の最大数を変更することができます。 SELECT ステートメントで 'batchsize' オプションを指定することによって行うことができます。 例:  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]今すぐ、一度に 1000 を超える行が取得され、したがって大量のメモリを消費しません。  
  
##  <a name="BKMK_SAPQueryExcep"></a>パラメーターと日付の値を取得するクエリの実行中に例外  
 **問題**  
  
 EXECQUERY がのコマンドを日付の値をとるパラメーターを使用してクエリを実行するときに、次の例外を取得します。  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 **原因**  
  
 EXECQUERY コマンドを使用してクエリを実行するときに、YYYYMMDD の形式で日付の値を必ず指定する必要があります。  
  
 **解決策**  
  
 YYYYMMDD 形式で日付の値を指定することを確認してください。 例:  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a>EXECQUERY コマンドを使用してクエリを実行する NO_VARIANT 例外  
 **問題**  
  
 EXECQUERY コマンドを使用してクエリを実行するときに、次の例外を取得します。  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 **原因**  
  
 この例外の 2 つの可能性のある原因ことができます。  
  
1.  実行しようとしているクエリは、SAP システムで定義されているバリエーションにあります。 バリアントは、保存されている SAP クエリの実行中に指定できる選択条件のセットを参照してください。 たとえば、バリアントを使用すると、クエリの既定値を指定します。  
  
2.  どちらを実行しようとしているクエリ バリアント型が定義されていることも、パラメーター値を渡すことが求められます。  
  
 **解決策**  
  
1.  1 の理由で、クエリに関連付けられているバリアントの名前を指定するになっていることを確認します。 例:  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
    ```  
  
2.  2 の理由で、クエリ コマンドを指定する際に、ダミーのパラメーターの名前と値を指定するになっていることを確認します。 たとえば、"myquery"クエリに実行する任意のパラメーターが必要としない場合、として EXECQUERY コマンドを指定する必要があります。  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
    ```  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)