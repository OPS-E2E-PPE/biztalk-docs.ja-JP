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
ms.openlocfilehash: 0a979b894715055b979ecae8c66ecb3fa19ba603
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018124"
---
# <a name="reporting-errors-from-pipeline-components"></a>パイプライン コンポーネントからエラーの報告
パイプライン コンポーネントは、2 種類の方法でエラーを報告します。  
  
-   .NET ベースのコンポーネントの場合は、例外をスローします。  
  
-   COM ベースのコンポーネントで設定して、 **ErrorInfo**オブジェクトと HRESULT エラーを返します。  
  
## <a name="reporting-errors-from-net-pipeline-components"></a>.NET パイプライン コンポーネントからのエラーの報告  
 .NET ベースのパイプライン コンポーネントは、エラーを報告するために、例外をスローしてエラーの説明を通知する必要があります。 エラーをスローするコンポーネントの名前を報告するには、設定、**ソース**のプロパティ、**例外**オブジェクト。  
  
 メッセージング エンジンを使用して、**メッセージ**と**ソース**のプロパティ、**例外**エラーを報告するオブジェクト。 次のメッセージがイベント ログに書き込まれます。  
  
 "が失敗した実行、[受信&#124;送信] パイプライン:\<パイプライン名\>ソース:\<ソース\>[受信場所&#124;送信ポート:]\<場所&#124;ポート名\>理由:\<メッセージ\>"。  
  
## <a name="reporting-errors-from-com-pipeline-components"></a>COM パイプライン コンポーネントからのエラーの報告  
 COM ベースのパイプライン コンポーネントは、エラーを報告するために以下のアクションを実行します。  
  
1. パイプライン コンポーネントのセット、 **IErrorInfo**オブジェクトを呼び出すことによって、 **SetErrorInfo**メソッド。  
  
2. パイプライン コンポーネントは、HRESULT エラーをメッセージング エンジンに返します。  
  
   メッセージング エンジンを使用して、 **GetSource**と**GetDescription**のプロパティ、 **IErrorInfo**エラーを報告するオブジェクト。 送信元が設定されていない場合は、コンポーネントの名前を使用します。 説明のセットまたは全体がない場合**ErrorInfo**オブジェクトが設定されていない、返された HRESULT は、説明ではなく報告されます。 次のメッセージがイベント ログに書き込まれます。  
  
   "が失敗した実行、[受信&#124;送信] パイプライン:\<パイプライン名\>ソース: \<GetSource\> [受信場所&#124;送信ポート:]\<場所&#124;ポート名\>理由: \<GetDescription または HRESULT\>"。  
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)