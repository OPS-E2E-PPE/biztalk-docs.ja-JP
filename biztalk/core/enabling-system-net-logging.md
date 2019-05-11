---
title: System.Net のログ記録を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eea50b9-1f46-45fc-a327-585adb4583a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7044d1455905c45995a3096b7ec3cc6c153adb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349624"
---
# <a name="enabling-systemnet-logging"></a>System.Net のログ記録を有効にします。
ログ記録を有効にすることができます、`System.Net`と`System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] BTSNtSvc.exe サービスの名前空間。 これを BizTalk Server インストールで問題を特定するのに役立つ情報を含むを作成する詳細なログ ファイルとなります。  
  
> [!NOTE]
>  これは、Microsoft の機能[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]で動作[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]またはそれ以降。  
  
 アプリケーション構成ファイルを変更することでトレースが有効になっている**BTSNtSvc.exe**、 **BTSNtSvc.exe.config**します。BizTalk Server のインストール パスで見つかんだことができます。既定の場所に BizTalk Server をインストールした場合 BtsNtSvc.exe はディレクトリには[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。  
  
 変更する**BTSNtSvc.exe.config**構成ファイルを開き、以下のコードを貼り付け、`<configuration>`メモ帳または使い慣れたテキスト エディターを使用して要素。  
  
```  
<system.diagnostics>  
  <sources>  
    <source name="System.Net" switchValue="Verbose">  
      <listeners>  
        <add name="System.Net"/>  
      </listeners>  
    </source>  
    <source name="System.Net.Sockets" switchValue="Verbose">  
      <listeners>  
        <add name="System.Net"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="System.Net"  
          type="System Diagnostics.TextWriterTraceListener"  
          initializeData="System.Net..log"/>  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 ログ ファイルは、BTSNtSvc.exe を含む同じディレクトリに書き込まれます。 既定の場所にインストールした場合に書き込まは[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。  
  
## <a name="see-also"></a>参照  
 [ネットワークのトレースの解釈](http://go.microsoft.com/fwlink/?LinkId=78679)