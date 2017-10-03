---
title: "BTSWebSvcWiz.exe.config を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, code samples
- Web services, debugging
ms.assetid: 8466e460-faa9-45ea-9586-19174858d194
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1686932099baa98f36af9ef8a2ca384f7f27a0ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-btswebsvcwizexeconfig"></a>BTSWebSvcWiz.exe.config を変更する方法
コメントを解除して、BizTalk Web サービス公開ウィザードをデバッグするトレースを有効にする、\<追加 > BTSWebSvcWiz.exe.config ファイル内のノードです。 トレース リスナ ノードのコメントが解除されている場合、 *initializeData*パラメーターは、変更されたが、BizTalk Server トレース ファイルに出力を書き込みます、現在のディレクトリ。 または、することができます、トレースのレベルを設定**ApplicationTraceSwitch**し、トレース ファイルのパス名を設定します。  
  
 BTSWebSvcWiz.exe.config は BTSWebSvcWiz.exe ファイルと同じディレクトリ (通常は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) に存在します。  
  
 次の例に示しますをコメント解除された\<追加 > BTSWebSvcWiz.exe.config ファイル内のノード。  
  
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
  
 このトレース機能では .NET Framework の Trace クラスを使用しています。 Trace クラスの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67886](http://go.microsoft.com/fwlink/?LinkId=67886)です。  
  
 について**TextWriterTraceListener**、「TextWriterTraceListener」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62267](http://go.microsoft.com/fwlink/?LinkId=62267)です。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスのデバッグ](../core/debugging-published-web-services.md)