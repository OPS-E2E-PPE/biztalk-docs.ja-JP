---
title: "受信ポート (BizTalk Server サンプル) の削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d15442da8afd4829245b742bdd45af8f7d1f832
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="remove-receive-port-biztalk-server-sample"></a>受信ポート (BizTalk Server サンプル) の削除
受信ポートの削除のサンプルでは、1 つ以上の受信ポートを削除する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。  
  
-   受信ポート名が指定されていることを前提として、クエリを実行し、一致する受信ポートの一覧を取得します。  
  
    > [!NOTE]
    >  通常、指定された名前に一致する受信ポートは 1 つだけです。  
  
-   取得した受信ポートを削除します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプルは、次の SDK の場所に配置されます。  
  
 \<*パスのサンプル*\>\Admin\WMI\Remove 受信 Port\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> RemoveReceivePort.vbs|削除する 1 つ以上の受信ポートを指定するパラメータを取る VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信ポートの削除のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Remove 受信 Port\VBScript\  
  
2.  cscript プログラムを使用し、次のコマンド ライン引数を渡して、ファイル RemoveReceivePort.vbs を実行します。  
  
     **\<** ***ReceivePortName* \>**です。 削除する受信ポートの名前。 受信ポート名に空白が含まれている場合は、名前を引用符で囲みます。  
  
     例:  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル RemoveReceivePort.vbs には、実行する操作についての説明が記された詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)