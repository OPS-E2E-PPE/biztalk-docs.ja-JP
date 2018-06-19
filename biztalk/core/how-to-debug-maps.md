---
title: マップをデバッグする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40964b267ad0788308a92490a106f940a6cb33e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249034"
---
# <a name="how-to-debug-maps"></a>マップをデバッグする方法
**マップのデバッグ**の識別と複雑なマッピングの問題を修正する便利な機能です。 このトピックでは、インライン XSLT デバッガーを使用したマップのデバッグ手順について説明します。  
  
> [!NOTE]
>  マップをデバッグするときに、**マップのデバッグ**機能は、マップ ファイルのプロパティを使用して**TestMap の入力インスタンス**と**TestMap 出力インスタンス**です。 そのため、マップをデバッグする前に、入力を構成して、マップ ファイルのインスタンスのプロパティを出力することを勧めします。  
  
### <a name="to-debug-a-biztalk-map"></a>BizTalk マップをデバッグするには  
  
1.  ソリューション エクスプ ローラーで、テスト、およびをクリックする地図を右クリックして**マップのデバッグ**です。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のエディターにマップが XSLT 形式で表示されます。  
  
2.  F10 キーまたは F11 キーを押して XSL コードをデバッグします。 Functoid の呼び出しで F11 キーを押すと、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] により Functoid の C# コードがステップ実行されます。 Functoid のソース コードで使用されている変数の値を、ローカルの Windows デバッガーで確認できます。