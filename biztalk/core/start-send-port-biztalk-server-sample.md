---
title: 送信ポートの開始 (BizTalk Server サンプル) |Microsoft ドキュメント
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
ms.openlocfilehash: f293d00848c32f6b519349543c8a39824d9bca8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973880"
---
# <a name="start-send-port-biztalk-server-sample"></a>送信ポートの開始 (BizTalk Server サンプル)
送信ポート開始のサンプルは、ファイル アダプタの使用時に、送信ポートを開始し、オプションでプライマリ トランスポート アドレスを設定する方法を示しています。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。  
  
-   送信ポート名が指定されていることを前提として、クエリを実行し、一致する送信ポートの一覧を取得します。  
  
    > [!NOTE]
    >  通常、指定された名前に一致する送信ポートは 1 つだけです。  
  
-   これらの送信ポートのプライマリ トランスポート アドレスを設定します (インストール パスの相対パスで指定)。  
  
-   開始される送信ポート。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプル ファイルは、次の SDK の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\WMI\Start Port\ の送信  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> StartSendPort.vbs|開始する送信ポートを指定するパラメータを取得すると共に、そのポートに関連付けられているプライマリ トランスポート アドレスの新しい値を必要に応じて取得する VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 送信ポート開始のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Start Port\VBScript\ の送信  
  
2.  cscript プログラムを使用し、次のコマンド ライン引数 (2 番目はオプション) を渡して、ファイル StartSendPort.vbs を実行します。  
  
    -   **\<** ***SendPortName* \>です。** 開始する送信ポートの名前。 送信ポートの名前にスペースが含まれる場合は、名前を引用符で囲みます。  
  
    -   **\<** ***PrimaryTransportAddress* \>です。** 製品のインストール場所を基準としたプライマリ トランスポート アドレス。この引数を指定することによって変更できます。 プライマリ アダプタ アドレスに空白が含まれている場合は、名前を引用符で囲みます。  
  
         例:  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル StartSendPort.vbs には、実行する操作についての説明のある詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)