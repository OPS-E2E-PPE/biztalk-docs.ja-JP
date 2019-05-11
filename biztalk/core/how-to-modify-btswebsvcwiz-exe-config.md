---
title: BTSWebSvcWiz.exe.config を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, code samples
- Web services, debugging
ms.assetid: 8466e460-faa9-45ea-9586-19174858d194
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc89d7a0e4201ae3bbff36c636a27c78b2b36b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384627"
---
# <a name="how-to-modify-btswebsvcwizexeconfig"></a><span data-ttu-id="cbb98-102">BTSWebSvcWiz.exe.config を変更する方法</span><span class="sxs-lookup"><span data-stu-id="cbb98-102">How to Modify BTSWebSvcWiz.exe.config</span></span>
<span data-ttu-id="cbb98-103">コメントを解除して、BizTalk Web サービス公開ウィザードをデバッグするトレースを有効にした、\<追加\>BTSWebSvcWiz.exe.config ファイル内のノード。</span><span class="sxs-lookup"><span data-stu-id="cbb98-103">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add\> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="cbb98-104">トレース リスナ ノードのコメントが解除されている場合、 *initializeData*パラメーターが変更されていない BizTalk サーバー トレース ファイルに出力を書き込みます、現在のディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="cbb98-104">If the trace listener node is uncommented and the *initializeData* parameter is unchanged, BizTalk Server writes the trace file output to the current directory.</span></span> <span data-ttu-id="cbb98-105">また、できるトレースのレベルを設定**ApplicationTraceSwitch**し、トレース ファイルのパス名を設定します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-105">Alternatively, you can set the trace level of **ApplicationTraceSwitch** and set the path name of the trace file.</span></span>  
  
 <span data-ttu-id="cbb98-106">BTSWebSvcWiz.exe.config は、通常は BTSWebSvcWiz.exe ファイルと同じディレクトリにある[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-106">BTSWebSvcWiz.exe.config is located in the same directory as the BTSWebSvcWiz.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="cbb98-107">コメント解除されたの一例を次に\<追加\>BTSWebSvcWiz.exe.config ファイル内のノード。</span><span class="sxs-lookup"><span data-stu-id="cbb98-107">The following is an example of an uncommented \<add\> node in BTSWebSvcWiz.exe.config file:</span></span>  
  
```  
<system.diagnostics>  
  <switches>  
    <!-- TraceLevel 0=Off, 1=Error, 2=Warning, 3=Info, 4=Verbose -->  
    <add name="ApplicationTraceSwitch" value="4" />  
  </switches>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <!--add name="Trace"  
       type="System.Diagnostics.TextWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
       initializeData="BTSWebSvcWiz.trace.log" /-->  
    </listeners>  
  </trace>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="cbb98-108">このトレース機能では、.NET Framework の Trace クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-108">This tracing feature uses the Trace class in the .NET Framework.</span></span> <span data-ttu-id="cbb98-109">Trace クラスの詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886)します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-109">For more information about the Trace class, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886).</span></span>  
  
 <span data-ttu-id="cbb98-110">について**TextWriterTraceListener**の「textwritertracelistener クラス」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267)します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-110">For information about **TextWriterTraceListener**, see "TextWriterTraceListener" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb98-111">参照</span><span class="sxs-lookup"><span data-stu-id="cbb98-111">See Also</span></span>  
 [<span data-ttu-id="cbb98-112">公開済み Web サービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="cbb98-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)