---
title: "送信ポートの削除 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bb37ae93b45ac1721da582cc0092bda5d67999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="remove-send-port-biztalk-server-sample"></a>送信ポートの削除 (BizTalk Server サンプル)
送信ポートの削除のサンプルでは、1 つ以上の送信ポートの参加を解除し、削除する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。  
  
-   送信ポート名が指定されていることを前提として、クエリを実行し、一致する送信ポートの一覧を取得します。  
  
    > [!NOTE]
    >  通常、指定された名前に一致する送信ポートは 1 つだけです。  
  
-   送信ポートの参加を解除します。  
  
-   削除された送信ポート。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*> \Admin\WMI\Remove Port\ の送信  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> RemoveSendPort.vbs|参加を解除し、削除する 1 つ以上の送信ポートを指定するパラメータを取る VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 送信ポートの削除のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-remove-send-port-sample"></a>送信ポートの削除のサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Admin\WMI\Remove Port\VBScript\ の受信  
  
2.  cscript プログラムを使用し、次のコマンド ライン引数を渡して、ファイル RemoveSendPort.vbs を実行します。  
  
     **\<**   
     ***SendPortName* >。** 削除する送信ポートの名前。 送信ポートの名前にスペースが含まれる場合は、名前を引用符で囲みます。  
  
     例:  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル RemoveSendPort.vbs には、実行する操作についての説明のある詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [管理 WMI (BizTalk Server Samples フォルダ)](../core/admin-wmi-biztalk-server-samples-folder.md)