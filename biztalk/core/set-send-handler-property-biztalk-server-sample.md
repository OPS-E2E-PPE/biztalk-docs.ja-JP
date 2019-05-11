---
title: 送信ハンドラー プロパティ (BizTalk Server サンプル) の設定 |Microsoft Docs
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
ms.openlocfilehash: b8d1abddd497ad1f6d20c18bf7e5ff580b1ddc1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393270"
---
# <a name="set-send-handler-property-biztalk-server-sample"></a>送信ハンドラー プロパティ (BizTalk Server サンプル) の設定します。
送信ハンドラ プロパティの設定のサンプルでは、簡易メール転送プロトコル (SMTP) の送信ハンドラの XML 構成情報を設定する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。  
  
-   一致する送信ハンドラの一覧についてはクエリの送信ハンドラー名を指定します。  
  
-   SMTP 送信ハンドラの XML 構成情報を設定します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 サンプル ファイルは、次の SDK の場所に配置されます。  
  
 \<*パスのサンプル*\>\Admin\WMI\Set 送信ハンドラー Property\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|\VBScript フォルダー。<br /><br /> ConfigureSMTP.vbs|SMTP を指定するパラメータを取る VBScript ファイルは送信ハンドラと差出人の電子メール アドレスです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 送信ハンドラ プロパティの設定のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a>送信ハンドラ プロパティの設定のサンプルを実行するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\WMI\Set 送信ハンドラー Property\VBScript\  
  
2.  ファイル ConfigureSMTP.vbs cscript プログラムを使用して、次のコマンドライン引数を渡して実行します。  
  
    -   **\<** ***SMTPServerName* \>します。** メールの送信に使用される SMTP サーバーの名前。  
  
    -   **\<** ***FromEmailAddress* \>します。** 差出人アドレスとして使用される電子メール アドレス。  
  
         以下に例を示します。  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a>コメント  
 BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。  
  
 スクリプト ファイル ConfigureSMTP.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。 詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。  
  
## <a name="see-also"></a>参照  
 [Admin-WMI (BizTalk Server Samples フォルダー)](../core/admin-wmi-biztalk-server-samples-folder.md)