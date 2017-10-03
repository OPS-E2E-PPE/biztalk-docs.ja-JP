---
title: "ESB 例外管理を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec20c447b184c2fdadf87f62f37f576f5100d08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-esb-exception-management"></a>ESB 例外管理を使用します。
エラーと例外といくつかの ESB で別の処理ステージ中にコンテキストの範囲で発生します。 このセクションでは、例外の処理に関する情報を提供し、ESB の管理ポータルで詳細情報を公開する方法について説明します。  
  
## <a name="overview"></a>概要  
 さまざまな方法で例外を処理する、[!INCLUDE[prague](../includes/prague-md.md)]など、エンタープライズ ライブラリなどのフレームワークを使用して、ソリューションです。 ただし、ESB と BizTalk Server を開発する場合は、メッセージ ベースの環境で作業しています。 BizTalk ソリューション内のすべてのメッセージ指向は、BizTalk 開発者は、メッセージ指向の方法で検討します。 したがって、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理へのメッセージ指向アプローチを実装します。  
  
 ESB 例外管理フレームワークの例外監視の柔軟なアプローチを提供し、ソリューションの外部でから発生するエラー応答を有効化するデザイン パターンに従っている — ビジネス単位レベルでおそらくです。  
  
 次のトピックでは、さらに詳しくは、ESB 例外管理フレームワークについて説明します。  
  
-   [ESB 例外管理フレームワークの設計](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [例外管理フレームワークのコンポーネント](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [例外管理フレームワークを使用します。](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [カスタム例外ハンドラーの作成](../esb-toolkit/creating-custom-exception-handlers.md)