---
title: "BizTalk Operations サンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6307f9d9e4ff9907bab22efcde0755dbdfdc228b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-biztalk-operations-sample"></a>BizTalk Operations サンプルをインストールします。
Microsoft BizTalk Operations サンプルには、ESB BizTalk 操作のサービスのインストールし、構成が必要です。 ESB BizTalk Operations サービスをインストールして、ESB 構成ツールを使用して構成するコア Web サービスの 1 つです。 ESB 構成ツールの使用に関する詳細については、次を参照してください[http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).。 BizTalk Operations Web サービスの既定の場所は http://localhost/ESB.BizTalkOperationsService/Operations.asmx;ただし、変更できますこのアプリケーション構成ファイル内の別の場所またはリモート サーバーでサービスを展開する場合。  
  
 ソリューションのプロジェクトからの BizTalk 操作サンプルをインストールする必要があります。  
  
 **BizTalk 操作サンプルをインストールするには**  
  
1.  インストールした \Source\Samples\BizTalkOperations フォルダーから ESB.BizTalkOperations.Test.Client.csproj をという名前のソリューションを開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]にサンプル[!INCLUDE[vs2010](../includes/vs2010-md.md)]です。  
  
2.  コマンドを使用、**ビルド**ソリューションをコンパイルするにはメニュー。