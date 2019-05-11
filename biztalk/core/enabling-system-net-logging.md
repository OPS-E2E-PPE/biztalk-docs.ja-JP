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
# <a name="enabling-systemnet-logging"></a><span data-ttu-id="e5b51-102">System.Net のログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5b51-102">Enabling System.Net Logging</span></span>
<span data-ttu-id="e5b51-103">ログ記録を有効にすることができます、`System.Net`と`System.Net.Sockets` [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] BTSNtSvc.exe サービスの名前空間。</span><span class="sxs-lookup"><span data-stu-id="e5b51-103">You can enable logging for the `System.Net` and `System.Net.Sockets`[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] namespace for the BTSNtSvc.exe service.</span></span> <span data-ttu-id="e5b51-104">これを BizTalk Server インストールで問題を特定するのに役立つ情報を含むを作成する詳細なログ ファイルとなります。</span><span class="sxs-lookup"><span data-stu-id="e5b51-104">This will cause a detailed log file to be created containing information that may help you identify issues with your BizTalk Server installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5b51-105">これは、Microsoft の機能[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]で動作[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]またはそれ以降。</span><span class="sxs-lookup"><span data-stu-id="e5b51-105">This is a feature of the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] and will work in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] or later.</span></span>  
  
 <span data-ttu-id="e5b51-106">アプリケーション構成ファイルを変更することでトレースが有効になっている**BTSNtSvc.exe**、 **BTSNtSvc.exe.config**します。BizTalk Server のインストール パスで見つかんだことができます。既定の場所に BizTalk Server をインストールした場合 BtsNtSvc.exe はディレクトリには[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e5b51-106">Tracing is enabled by modifying the application configuration file for **BTSNtSvc.exe**,  **BTSNtSvc.exe.config**. It can be found in the BizTalk Server installation path; if you installed BizTalk Server to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="e5b51-107">変更する**BTSNtSvc.exe.config**構成ファイルを開き、以下のコードを貼り付け、`<configuration>`メモ帳または使い慣れたテキスト エディターを使用して要素。</span><span class="sxs-lookup"><span data-stu-id="e5b51-107">To modify **BTSNtSvc.exe.config**, open the configuration file and paste the code below into the `<configuration>` element using Notepad or your favorite text editor.</span></span>  
  
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
  
 <span data-ttu-id="e5b51-108">ログ ファイルは、BTSNtSvc.exe を含む同じディレクトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e5b51-108">The log file will be written to the same directory that contains BTSNtSvc.exe.</span></span> <span data-ttu-id="e5b51-109">既定の場所にインストールした場合に書き込まは[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e5b51-109">If you installed to the default location, it will be written to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b51-110">参照</span><span class="sxs-lookup"><span data-stu-id="e5b51-110">See Also</span></span>  
 [<span data-ttu-id="e5b51-111">ネットワークのトレースの解釈</span><span class="sxs-lookup"><span data-stu-id="e5b51-111">Interpreting Network Tracing</span></span>](http://go.microsoft.com/fwlink/?LinkId=78679)