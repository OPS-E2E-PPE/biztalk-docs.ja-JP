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
ms.openlocfilehash: c4eff5a729b8c8ca191b2185180e312f9e895c02
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="using-esb-exception-management"></a>ESB 例外管理を使用します。
エラーと例外といくつかの ESB で別の処理ステージ中にコンテキストの範囲で発生します。 このセクションでは、例外の処理に関する情報を提供し、ESB の管理ポータルで詳細情報を公開する方法について説明します。  
  
## <a name="overview"></a>概要  
 など、エンタープライズ ライブラリなどのフレームワークを使用して、BizTalk Server ソリューションでの例外を処理する方法はたくさんあります。 ただし、ESB と BizTalk Server を開発する場合は、メッセージ ベースの環境で作業しています。 BizTalk ソリューション内のすべてのメッセージ指向は、BizTalk 開発者は、メッセージ指向の方法で検討します。 したがって、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理へのメッセージ指向アプローチを実装します。  
  
 ESB 例外管理フレームワークの例外監視の柔軟なアプローチを提供し、ソリューションの外部でから発生するエラー応答を有効化するデザイン パターンに従っている — ビジネス単位レベルでおそらくです。  
  
 次のトピックでは、さらに詳しくは、ESB 例外管理フレームワークについて説明します。  
  
-   [ESB 例外管理フレームワークの設計](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [例外管理フレームワークのコンポーネント](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [例外管理フレームワークを利用する](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [カスタム例外ハンドラーを作成する](../esb-toolkit/creating-custom-exception-handlers.md)