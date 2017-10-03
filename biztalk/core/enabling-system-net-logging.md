---
title: "System.Net のログ記録を有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eea50b9-1f46-45fc-a327-585adb4583a0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e672f2b9e7ae8b0ef3889493273660c8ef9140c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-systemnet-logging"></a>System.Net のログ記録の有効化
ログ記録を有効にすることができます、`System.Net`と`System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] BTSNtSvc.exe サービスの名前空間。 これにより、BizTalk Server のインストールでの問題の特定に役立つ情報が記録された詳細なログ ファイルを作成できます。  
  
> [!NOTE]
>  これは、Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] の機能の 1 つであり、[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 以降に対応しています。  
  
 アプリケーション構成ファイルを変更することでトレースが有効になっている**BTSNtSvc.exe**、 **BTSNtSvc.exe.config**です。このファイルは BizTalk Server のインストール パスにあります。つまり、BizTalk Server が既定の場所にインストールされていれば、BtsNtSvc.exe は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] ディレクトリにあります。  
  
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