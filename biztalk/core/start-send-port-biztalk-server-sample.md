---
title: 送信ポートの開始 (BizTalk Server サンプル) |Microsoft Docs
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
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca8ab34acb7fb49164a3e0cd0ff99f765e41912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393055"
---
# <a name="start-send-port-biztalk-server-sample"></a>送信ポートの開始 (BizTalk Server サンプル)
送信ポートの開始のサンプルでは、送信ポートを開始し、必要に応じて、ファイル アダプターを使用する場合にプライマリ トランスポート アドレスを設定する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。  
  
-   一致する送信ポートの一覧については、クエリの送信ポート名を指定します。  
  
    > [!NOTE]
    >  一般に、のみがあります指定された名前に一致する 1 つの送信ポート。  
  
-   これらの送信のプライマリ トランスポート アドレス (インストール パスの相対) のポートを設定します。  
  
-   開始送信ポート。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプル ファイルは、次の SDK の場所に配置されます。  
  
 \<*パスのサンプル*\>\Admin\WMI\Start Port\ を送信します。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> StartSendPort.vbs|パラメーターを取る VBScript ファイルを開始する送信ポートを指定して、必要に応じて、プライマリ トランスポート アドレスの新しい値をそのポートに関連付けられています。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 送信ポートの開始のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Start Port\VBScript\ を送信します。  
  
2.  ファイル StartSendPort.vbs cscript プログラムを使用して次のコマンドライン引数を渡すことが 2 つ目は省略可能な実行します。  
  
    -   **\<** ***SendPortName* \>.** 開始する送信ポートの名前。 送信ポートの名前にスペースが含まれている場合は、名前を引用符で囲みます。  
  
    -   **\<** ***PrimaryTransportAddress* \>します。** この引数を指定することで変更可能な製品のインストール場所を基準とした、プライマリ トランスポート アドレス。 プライマリ アダプタ アドレスにスペースが含まれている場合は、名前を引用符で囲みます。  
  
         以下に例を示します。  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル StartSendPort.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)