---
title: "例外を処理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 004e4f29bcfc292edb33bae816a52b588a89771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-exceptions-are-handled"></a>例外の処理方法
スコープ内で例外が発生すると、スコープ内の実行の各論理スレッドは停止します。 ランタイム エンジンでは、該当する例外の例外ハンドラーが検索されます。  
  
 特定の例外や、基本的な例外のいずれかに一致する例外ハンドラーが見つかった場合は、制御がその例外ハンドラーに渡されて、コードが実行されます。  
  
> [!NOTE]
>  例外の種類はから派生する必要があります**System.Exception**です。  
  
 例外ハンドラーはシーケンシャルであり、特定の例外を処理できるかどうかを確認するためにチェックされます。 正しく機能させるためには、最初により特定の種類の例外を処理し、続いて一般的な種類の例外の処理となっていくように配置する必要があります。 これは、特定の種類の例外が、基本的な例外を処理するためのハンドラーではなく、適切なハンドラーによって確実に処理されるようにするためです。  
  
 例外ハンドラーが正常に終了すると、制御が前後のスコープに渡されます。 前後のスコープで例外がスローされていない場合、オーケストレーションはそのまま実行されます。 例外ハンドラーが throw ステートメントで終了すると、スローされる別の例外を指定していない限り、対象となる前後のスコープに対して元の例外が再びスローされます。  
  
 例外ハンドラーが見つからない場合は、既定の例外ハンドラーが実行されます。 スコープの既定の例外ハンドラーは、ネストされたトランザクションの補正を呼び出してから、例外を再度スローします。 独自の例外ハンドラーを記述する場合は、例外を反映しないように選択することができます。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)