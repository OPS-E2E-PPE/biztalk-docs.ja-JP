---
title: Catch の例外 Block3 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35746e0bc8e9bbadb8deffb5287943a95fd77e77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343951"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。 多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。  
  
 さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。 各例外ハンドラーでエラー メッセージまたはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する**System.Exception**します。 例外ブロックは、一般的な例外ハンドラーとして扱われますから派生していない例外をキャッチできる例外の種類を指定しない場合**System.Exception**します。  
  
 例外がスローされた例外ハンドラーで指定された型と一致する場合は、その例外ハンドラーが呼び出されます。 その他の例外がスローされた場合は、既定の例外ハンドラーによって処理されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。  
  
### <a name="to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加するには  
  
1.  右クリックし、**スコープ**図形を追加する、**例外のキャッチ**ブロックし、クリックして**新しい例外ハンドラー**します。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。  
  
2.  [プロパティ] ウィンドウでは、次のプロパティを指定します。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |例外オブジェクト名|例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。|  
    |例外オブジェクト型|オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。|  
  
3.  内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。  
  
> [!NOTE]
>  汎用的な例外を指定する場合、**例外**オブジェクトの種類を**例外のキャッチ**ブロックから派生していないものも含め、すべての例外をインターセプトする**System.Exception**. このような場合は、例外オブジェクトへのアクセスを必要するはありません。 使用する場合、このブロック内で、**例外のスロー**図形に、一般的な例外の種類が効率的に再スロー例外をキャッチしました。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)