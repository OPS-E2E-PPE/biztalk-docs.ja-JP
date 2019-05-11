---
title: 受信場所 (BizTalk Server サンプル) の有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f41353b17a3e393d865c381a5f6b6b15cb676cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349725"
---
# <a name="enable-receive-location-biztalk-server-sample"></a>受信場所 (BizTalk Server サンプル) を有効にします。
受信場所の有効化のサンプルでは、受信場所を有効にし、必要に応じてその受信場所の受信トランスポート URL を設定する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Microsoft Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。  
  
-   受信ポート名と一致する受信場所の一覧については、クエリの受信場所を指定します。  
  
-   (インストール パスの相対) の受信場所の受信トランスポート URL を設定します。  
  
-   受信場所を有効にします。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\WMI\Enable Location\ の受信  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> EnableRecLoc.vbs|パラメーターを取る VBScript ファイルが有効にする受信場所を指定して、受信トランスポート URL の新しい値が必要に応じて、その受信場所に関連付けられています。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信場所の有効化のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Enable Location\VBScript\ の受信  
  
2.  ファイル EnableRecLoc.vbs cscript プログラムを使用して、3 つ目は省略可能ですが、次のコマンドライン引数を渡すことを実行します。  
  
    -   **\<** ***ReceivePortName* \>します。** 有効にする受信場所を含む受信ポートの名前。 受信ポート名にスペースが含まれている場合は、名前を引用符で囲みます。  
  
    -   **\<** ***ReceiveLocationName* \>.** 有効にするために指定した受信ポートで受信場所の名前。 受信場所の名前にスペースが含まれている場合は、名前を引用符で囲みます。  
  
    -   **\<** ***InboundTransportURI* \>します。** この引数を指定することで変更可能な製品のインストール場所を基準とした受信アダプターの URI。 受信アダプタ URI にスペースが含まれている場合は、URI を引用符で囲みます。  
  
         例 :  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         -または-  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル EnableRecLoc.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。  
  
 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)