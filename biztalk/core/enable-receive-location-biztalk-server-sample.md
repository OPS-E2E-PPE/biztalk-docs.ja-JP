---
title: "有効にする受信場所 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2df85f051285e999660dc3765855d22c708939
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="enable-receive-location-biztalk-server-sample"></a>有効にする受信場所 (BizTalk Server サンプル)
受信場所の有効化のサンプルでは、受信場所を有効にする方法を示します。オプションで、その受信場所の受信トランスポート URL を設定する方法を説明します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成しているスクリプト ファイル内の Microsoft Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダを使用した次の操作の実行方法を示しています。  
  
-   受信ポート名と受信場所が指定されていることを前提として、クエリを実行し、一致する受信場所の一覧を取得します。  
  
-   受信場所の受信トランスポート URL を設定します (インストール パスの相対パスで指定)。  
  
-   受信場所を有効にします。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\WMI\Enable 受信 Location\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> EnableRecLoc.vbs|有効にする受信場所を指定するパラメータを受け取り、必要に応じてその受信場所に関連付けられている受信トランスポート URL の新しい値を受け取る VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 受信場所の有効化のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Enable 受信 Location\VBScript\  
  
2.  cscript プログラムを使用し、次のコマンド ライン引数 (3 番目はオプション) を渡して、ファイル EnableRecLoc.vbs を実行します。  
  
    -   **\<** ***ReceivePortName* \>です。** 有効にする受信場所を含む受信ポートの名前。 受信ポート名に空白が含まれている場合は、名前を引用符で囲みます。  
  
    -   **\<** ***ReceiveLocationName* \>です。** 指定の受信ポート内にある、有効にする受信場所の名前。 受信場所名に空白が含まれている場合は、名前を引用符で囲みます。  
  
    -   **\<** ***InboundTransportURI* \>です。** 製品のインストール場所に相対的な受信アダプタ URI。この引数を指定することによって変更できます。 受信アダプタ URI に空白が含まれている場合は、URI を引用符で囲みます。  
  
         例:  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         - または -  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル EnableRecLoc.vbs には、実行する操作についての説明が記された詳細なコメントが含まれています。  
  
 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)