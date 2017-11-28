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
# <a name="enabling-systemnet-logging"></a><span data-ttu-id="cb068-102">System.Net のログ記録の有効化</span><span class="sxs-lookup"><span data-stu-id="cb068-102">Enabling System.Net Logging</span></span>
<span data-ttu-id="cb068-103">ログ記録を有効にすることができます、`System.Net`と`System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] BTSNtSvc.exe サービスの名前空間。</span><span class="sxs-lookup"><span data-stu-id="cb068-103">You can enable logging for the `System.Net` and `System.Net.Sockets`[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] namespace for the BTSNtSvc.exe service.</span></span> <span data-ttu-id="cb068-104">これにより、BizTalk Server のインストールでの問題の特定に役立つ情報が記録された詳細なログ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cb068-104">This will cause a detailed log file to be created containing information that may help you identify issues with your BizTalk Server installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb068-105">これは、Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] の機能の 1 つであり、[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 以降に対応しています。</span><span class="sxs-lookup"><span data-stu-id="cb068-105">This is a feature of the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] and will work in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] or later.</span></span>  
  
 <span data-ttu-id="cb068-106">アプリケーション構成ファイルを変更することでトレースが有効になっている**BTSNtSvc.exe**、 **BTSNtSvc.exe.config**です。このファイルは BizTalk Server のインストール パスにあります。つまり、BizTalk Server が既定の場所にインストールされていれば、BtsNtSvc.exe は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="cb068-106">Tracing is enabled by modifying the application configuration file for **BTSNtSvc.exe**,  **BTSNtSvc.exe.config**. It can be found in the BizTalk Server installation path; if you installed BizTalk Server to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="cb068-107">変更する**BTSNtSvc.exe.config**構成ファイルを開き、以下のコードを貼り付け、`<configuration>`メモ帳または使い慣れたテキスト エディターを使用して要素。</span><span class="sxs-lookup"><span data-stu-id="cb068-107">To modify **BTSNtSvc.exe.config**, open the configuration file and paste the code below into the `<configuration>` element using Notepad or your favorite text editor.</span></span>  
  
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
  
 <span data-ttu-id="cb068-108">ログ ファイルは、BTSNtSvc.exe を含む同じディレクトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cb068-108">The log file will be written to the same directory that contains BTSNtSvc.exe.</span></span> <span data-ttu-id="cb068-109">既定の場所にインストールした場合に書き込まは[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cb068-109">If you installed to the default location, it will be written to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb068-110">参照</span><span class="sxs-lookup"><span data-stu-id="cb068-110">See Also</span></span>  
 [<span data-ttu-id="cb068-111">ネットワークのトレースの解釈</span><span class="sxs-lookup"><span data-stu-id="cb068-111">Interpreting Network Tracing</span></span>](http://go.microsoft.com/fwlink/?LinkId=78679)