---
title: 受信ポート (BizTalk Server サンプル) の削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f39d8264e00b239eaffbb24fb53e3a0f99998720
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397943"
---
# <a name="remove-receive-port-biztalk-server-sample"></a>受信ポート (BizTalk Server サンプル) の削除
以上の受信ポートや受信ポートの削除のサンプルが 1 つを削除する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。  
  
-   受信ポート名、一致する受信ポートの一覧については、クエリを指定します。  
  
    > [!NOTE]
    >  一般に、あるは 1 つだけ指定した名前に一致するポートを受信します。  
  
-   削除された受信ポート。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプルは、次の SDK の場所に配置されます。  
  
 \<*パスのサンプル*\>\Admin\WMI\Remove Port\ の受信  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> RemoveReceivePort.vbs|1 つまたは複数を指定するパラメーターを取る VBScript ファイルの受信ポートを削除します。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信ポートの削除のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Remove Port\VBScript\ の受信  
  
2.  ファイル RemoveReceivePort.vbs cscript プログラムを使用して、次のコマンドライン引数を渡して実行します。  
  
     **\<** ***ReceivePortName* \>** します。 削除する受信ポートの名前。 受信ポート名にスペースが含まれている場合は、名前を引用符で囲みます。  
  
     例 :  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル RemoveReceivePort.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)