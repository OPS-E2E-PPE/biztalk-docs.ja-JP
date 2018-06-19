---
title: Catch 例外 Block3 を追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 1040a27a5e1273d2ad80a722deb421878de36c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247058"
---
# <a name="how-to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加する方法
**例外のキャッチ**ブロックが例外ハンドラーを表します。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。 数だけ接続できます**例外のキャッチ**ブロックする必要があります。  
  
 例外ハンドラーを設定すると、各種の例外を処理することができます。 各例外ハンドラーでエラー メッセージまたはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する**System.Exception**です。 例外ブロックが、一般的な例外ハンドラーとして扱われますおよびからは派生しません例外をキャッチすることができる場合は、例外の種類を指定しないと、 **System.Exception**です。  
  
 例外ハンドラーで指定した種類に一致する例外がスローされると、その例外ハンドラーが呼び出されます。 その他の型の例外がスローされた場合、その例外は既定の例外ハンドラーによって処理されます。  
  
> [!NOTE]
>  追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクション タイプ**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。  
  
### <a name="to-add-a-catch-exception-block"></a>例外のキャッチ ブロックを追加するには  
  
1.  右クリックし、**スコープ**図形を追加する、**例外のキャッチ**をクリックして、ブロック**新しい例外ハンドラー**です。  
  
     A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。  
  
2.  [プロパティ] ウィンドウで、次のプロパティを指定します。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |例外オブジェクト名|例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。|  
    |例外オブジェクト型|この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。|  
  
3.  内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。  
  
> [!NOTE]
>  汎用的な例外を指定する場合、**例外**オブジェクトの種類を**例外のキャッチ**ブロックから派生していないものも含め、すべての例外をインターセプトする**System.Exception**. この場合、例外オブジェクトにアクセスすることはできません。 使用する場合、このブロック内で、**例外のスロー**図形に、一般的な例外の種類がする効率的に再スロー例外をキャッチしました。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)