---
title: パイプライン コンポーネントからエラーの報告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 043ecab38e664d332ab10018d28189db8bb0277d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397884"
---
# <a name="reporting-errors-from-pipeline-components"></a>パイプライン コンポーネントからエラーの報告
パイプライン コンポーネントは、2 つの方法でのエラーを報告します。  
  
-   。NET ベースのコンポーネントを例外をスローします。  
  
-   COM ベースのコンポーネントで設定して、 **ErrorInfo**オブジェクトと HRESULT エラーを返します。  
  
## <a name="reporting-errors-from-net-pipeline-components"></a>.NET パイプライン コンポーネントからエラーの報告  
 エラーを報告します。NET ベースのパイプライン コンポーネントは、エラーの説明を報告する例外をスローする必要があります。 エラーをスローするコンポーネントの名前を報告するには、設定、**ソース**のプロパティ、**例外**オブジェクト。  
  
 メッセージング エンジンを使用して、**メッセージ**と**ソース**のプロパティ、**例外**エラーを報告するオブジェクト。 次のメッセージがイベント ログに書き込まれます。  
  
 "が失敗した実行中、[受信&#124;送信] パイプライン:\<パイプライン名\>ソース。\<ソース\>[受信場所&#124;送信ポート:]\<場所&#124;ポート名\>理由。\<メッセージ\>"。  
  
## <a name="reporting-errors-from-com-pipeline-components"></a>COM パイプライン コンポーネントからエラーの報告  
 エラーを報告するには、COM ベースのパイプライン コンポーネントは、次の操作を実行します。  
  
1. パイプライン コンポーネントのセット、 **IErrorInfo**オブジェクトを呼び出すことによって、 **SetErrorInfo**メソッド。  
  
2. パイプライン コンポーネントは、メッセージング エンジンに報告された HRESULT エラーを返します。  
  
   メッセージング エンジンを使用して、 **GetSource**と**GetDescription**のプロパティ、 **IErrorInfo**エラーを報告するオブジェクト。 ソースが設定されていない場合は、コンポーネントの名前が使用されます。 説明のセットまたは全体がない場合**ErrorInfo**オブジェクトが設定されていない、返された HRESULT は、説明ではなく報告されます。 次のメッセージがイベント ログに書き込まれます。  
  
   "が失敗した実行中、[受信&#124;送信] パイプライン:\<パイプライン名\>ソース。\<GetSource\> [受信場所&#124;送信ポート:]\<場所&#124;ポート名\>理由。\<GetDescription または HRESULT\>"。  
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)