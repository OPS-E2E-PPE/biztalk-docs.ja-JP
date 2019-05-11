---
title: 例外を処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc50f8371e5417662a8b81ef119e2a33f18e8925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344137"
---
# <a name="how-exceptions-are-handled"></a>例外の処理方法
スコープ内で例外が発生する、スコープ内での実行の各論理スレッドが停止します。 ランタイム エンジンは、適切な例外の例外ハンドラーが検索しようとします。  
  
 特定の型またはその基本型のいずれかに一致する例外ハンドラーが見つかった場合は、コントロールは実行をそのハンドラーとそのコードに渡します。  
  
> [!NOTE]
>  例外の種類はから派生する必要があります**System.Exception**します。  
  
 例外ハンドラーはシーケンシャルです。つまり、特定の例外を処理できるかどうかに表示するにはチェックされます。 適切に機能するには、一般的な種類の処理後に特定の種類の処理が最初に、ように、例外ハンドラーを配置する必要があります。 これは、特定の種類の例外が 1 つの基本データ型を処理するように設計ではなく、適切なハンドラーによって処理されることを確認できるようにします。  
  
 例外ハンドラーが正常に完了した場合は、前後のスコープに制御が渡されます。 前後のスコープで例外がスローされていない場合、オーケストレーションを実行し続けます。 例外ハンドラーは、throw ステートメントで終わる、元の例外がスローする別の例外を指定しない限り、対象となる前後のスコープに対してもう一度スローされます。  
  
 例外ハンドラーが見つからない、既定の例外ハンドラーが実行されます。 スコープの既定の例外ハンドラーは、入れ子になったトランザクションの補正を呼び出すし、もう一度例外をスローします。 独自の例外ハンドラーを記述する場合は、例外を反映するには、しないこともできます。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)