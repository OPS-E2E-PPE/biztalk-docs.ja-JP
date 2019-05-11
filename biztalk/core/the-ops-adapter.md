---
title: Ops アダプタ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 052fff3518e3a302c6b632e9852a9d0c8f6b5ceb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277943"
---
# <a name="the-ops-adapter"></a>Ops アダプタ
ソリューションの設計は、渡すには、可能であれば、問題を示すメッセージとエラーを修正するか、終了順序を決定するオペレーション システムにエラーです。 新しいエラー報告機能を組み合わせて、Ops アダプタは、多くの場合を処理します。  
  
 ソリューションでは、新しいエラー報告機能を使用するように構成のポートでアダプターを使用します。 アダプターが 2 つのメソッドを呼び出してエラーを受信した場合**初期化**と**Execute**、指定したアセンブリ内のクラスにします。 ソリューションでは、これらのメソッドは、正しい操作グループに、エラーを送信します。  
  
 ソリューションには、独自に作成し、その他のソリューションでアダプターを使用できますが、簡単にサンプルのハンドラーが含まれています。 新しいエラー報告機能については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。  
  
> [!NOTE]
>  Ops アダプタは、アダプター フレームワークを使用して構築されています。 アダプタ フレームワークを構築する方法については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。  
  
 このセクションでは、アダプターのしくみと、それを構成する方法について説明し、ハンドラー アセンブリ エラーの詳細を提供します。 セクションの最後で、アダプターを変更またはその他のアプリケーションで使用するユーザーのために、役立つ実装の詳細。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Ops アダプタの使用](../core/using-the-ops-adapter.md)  
  
-   [サンプル操作エラー ハンドラー](../core/the-sample-operations-error-handler.md)  
  
-   [Ops アダプターの実装の詳細](../core/ops-adapter-implementation-details.md)