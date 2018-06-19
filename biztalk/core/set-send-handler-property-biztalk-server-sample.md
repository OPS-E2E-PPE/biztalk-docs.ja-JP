---
title: 送信ハンドラ プロパティ (BizTalk Server サンプル) を設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- send handlers, properties
ms.assetid: eb6ae2f2-528f-44ec-bca4-f37006893ff2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f783f465feff207ae1759ea358b0b848ccc0f4c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974584"
---
# <a name="set-send-handler-property-biztalk-server-sample"></a>送信ハンドラー プロパティ (BizTalk Server サンプル) を設定します。
送信ハンドラ プロパティの設定のサンプルでは、簡易メール送信プロトコル (SMTP) 送信ハンドラの XML 構成情報を設定する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。  
  
-   送信ハンドラ名が指定されていることを前提として、クエリを実行し、一致する送信ハンドラの一覧を取得します。  
  
-   SMTP 送信ハンドラの XML 構成情報を設定します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプル ファイルは、次の SDK の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\WMI\Set 送信ハンドラー Property\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|\VBScript フォルダー内のファイル : <br /><br /> ConfigureSMTP.vbs|SMTP 送信ハンドラと差出人の電子メール アドレスを指定するパラメータを取る VBScript ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 送信ハンドラ プロパティの設定のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a>送信ハンドラ プロパティの設定のサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Set 送信ハンドラー Property\VBScript\  
  
2.  cscript プログラムを使用し、次のコマンド ライン引数を渡して、ファイル ConfigureSMTP.vbs を実行します。  
  
    -   **\<** ***SMTPServerName* \>です。** メールの送信に使用する SMTP サーバーの名前。  
  
    -   **\<** ***FromEmailAddress* \>です。** 差出人のアドレスに使用される電子メール アドレス。  
  
         例:  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル ConfigureSMTP.vbs には、実行する操作についての説明のある詳細なコメントが含まれています。 詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)