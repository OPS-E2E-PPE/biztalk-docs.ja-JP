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
# <a name="how-to-modify-btswebsvcwizexeconfig"></a>BTSWebSvcWiz.exe.config を変更する方法
コメントを解除して、BizTalk Web サービス公開ウィザードをデバッグするトレースを有効にした、\<追加\>BTSWebSvcWiz.exe.config ファイル内のノード。 トレース リスナ ノードのコメントが解除されている場合、 *initializeData*パラメーターが変更されていない BizTalk サーバー トレース ファイルに出力を書き込みます、現在のディレクトリ。 また、できるトレースのレベルを設定**ApplicationTraceSwitch**し、トレース ファイルのパス名を設定します。  
  
 BTSWebSvcWiz.exe.config は、通常は BTSWebSvcWiz.exe ファイルと同じディレクトリにある[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。  
  
 コメント解除されたの一例を次に\<追加\>BTSWebSvcWiz.exe.config ファイル内のノード。  
  
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
  
 このトレース機能では、.NET Framework の Trace クラスを使用します。 Trace クラスの詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886)します。  
  
 について**TextWriterTraceListener**の「textwritertracelistener クラス」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267)します。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスのデバッグ](../core/debugging-published-web-services.md)