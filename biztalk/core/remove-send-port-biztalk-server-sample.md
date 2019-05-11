---
title: 送信ポートの削除 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4edb148d1627d596f98684b09d18da111b4e435c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397932"
---
# <a name="remove-send-port-biztalk-server-sample"></a>送信ポートの削除 (BizTalk Server サンプル)
以上の送信ポートや送信ポートの削除のサンプルが参加を解除し、1 つを削除する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。  
  
-   一致する送信ポートの一覧については、クエリの送信ポート名を指定します。  
  
    > [!NOTE]
    >  一般に、のみがあります指定された名前に一致する 1 つの送信ポート。  
  
-   参加が解除された送信ポート。  
  
-   削除された送信ポート。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\WMI\Remove Port\ を送信します。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> RemoveSendPort.vbs|1 つまたは複数を指定するパラメーターを取る VBScript ファイルでは、参加を解除し、削除するポートを送信します。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 送信ポートの削除のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-remove-send-port-sample"></a>送信ポートの削除のサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Remove Port\VBScript\ の受信  
  
2.  ファイル RemoveSendPort.vbs cscript プログラムを使用して、次のコマンドライン引数を渡して実行します。  
  
     **\<** ***SendPortName* \>.** 削除する送信ポートの名前。 送信ポートの名前にスペースが含まれている場合は、名前を引用符で囲みます。  
  
     例 :  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル RemoveSendPort.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)