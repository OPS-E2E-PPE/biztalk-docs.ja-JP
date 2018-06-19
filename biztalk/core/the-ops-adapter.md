---
title: Ops アダプタ |Microsoft ドキュメント
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
ms.openlocfilehash: 67463adf4e1e960ab6608e67595a679804aa223e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279378"
---
# <a name="the-ops-adapter"></a>Ops アダプタ
このソリューションは、エラーの修正や注文の中止に関して決定を行うオペレーティング システムに、問題を示すメッセージやエラーが可能な限り渡されるようにデザインされています。 Ops アダプタは新しいエラー報告機能を使用して、このような状況を処理します。  
  
 このソリューションでは、新しいエラー報告機能が有効に設定されているポートでアダプタを使用します。 アダプターが 2 つのメソッドを呼び出してエラーを受け取ることと、**初期化**と**Execute**、指定したアセンブリ内のクラスにします。 このソリューションでは、これらのメソッドがエラーを正しい操作グループに送信します。  
  
 サンプル ハンドラがソリューションに含まれていますが、独自のハンドラを簡単に作成して、アダプタを他のソリューションで使用することができます。 新しいエラー報告機能に関する概要については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。  
  
> [!NOTE]
>  Ops アダプタは、アダプター フレームワークを使用して作成されています。 フレームワークでアダプタのビルドについては、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。  
  
 このセクションでは、アダプタのしくみとその設定方法と、エラー ハンドラ アセンブリについて詳しく説明します。 このセクションの最後では、アダプタを変更したり、他の用途に使用するユーザーに役立つ実装の詳細を説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Ops アダプタの使用](../core/using-the-ops-adapter.md)  
  
-   [サンプル操作エラー ハンドラ](../core/the-sample-operations-error-handler.md)  
  
-   [Ops アダプタの実装の詳細](../core/ops-adapter-implementation-details.md)