---
title: マップをデバッグする方法 |Microsoft Docs
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
ms.openlocfilehash: f30d26b7c722ea4e4896bc7d19130e41eec5c719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989723"
---
# <a name="how-to-debug-maps"></a>マップをデバッグする方法
**マップのデバッグ**識別および複雑なマッピングの問題を修正する便利な機能です。 このトピックでは、インライン XSLT デバッガーを使用したマップのデバッグ手順について説明します。  

> [!NOTE]
>  マップをデバッグするときに、**マップのデバッグ**機能は、マップ ファイルのプロパティを使用して**TestMap の入力インスタンス**と**TestMap 出力インスタンス**します。 そのため、マップをデバッグする前に、入力を構成し、マップ ファイルにインスタンスのプロパティを出力することを勧めします。  

### <a name="to-debug-a-biztalk-map"></a>BizTalk マップをデバッグするには  

1. ソリューション エクスプ ローラーで、テスト、およびクリックするマップを右クリックして**マップのデバッグ**します。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のエディターにマップが XSLT 形式で表示されます。  

2. F10 キーまたは F11 キーを押して XSL コードをデバッグします。 Functoid の呼び出しで F11 キーを押すと、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] により Functoid の C# コードがステップ実行されます。 Functoid のソース コードで使用されている変数の値を、ローカルの Windows デバッガーで確認できます。
