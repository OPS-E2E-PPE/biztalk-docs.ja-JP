---
title: ESB 例外管理を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f3f44f7575c42b4719e6b05431178212c36210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396430"
---
# <a name="using-esb-exception-management"></a>ESB 例外管理を使用します。
エラーと例外については、いくつかの ESB で別の処理ステージ中にコンテキストの範囲で発生します。 このセクションでは、例外の処理に関する情報を提供し、ESB 管理ポータルの詳細を公開する方法について説明します。  
  
## <a name="overview"></a>概要  
 BizTalk Server ソリューションでは、Enterprise Library などのフレームワークの使用などの例外を処理するために多くの方法はあります。 ただし、ESB と BizTalk Server で開発する場合は、メッセージ ベースの環境で作業しています。 メッセージ指向では、BizTalk ソリューション内のすべてと、BizTalk 開発者は、メッセージ指向の方法で検討します。 そのため、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理へのメッセージ指向のアプローチを実装します。  
  
 ESB 例外管理フレームワークが例外を監視する柔軟なアプローチを提供し、ソリューションの外部から発生するエラー応答に使用する設計パターンに従います: business ユニット レベルでおそらくします。  
  
 次のトピックでは、さらに詳しく ESB 例外管理フレームワークについて説明します。  
  
-   [ESB 例外管理フレームワークの設計](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [例外管理フレームワークのコンポーネント](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [例外管理フレームワークを利用する](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [カスタム例外ハンドラーを作成する](../esb-toolkit/creating-custom-exception-handlers.md)