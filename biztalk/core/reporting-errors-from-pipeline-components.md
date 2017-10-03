---
title: "パイプライン コンポーネントからエラーを報告 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d181f557d64152ff79f70b09986c05727076121
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reporting-errors-from-pipeline-components"></a>パイプライン コンポーネントからエラーの報告
パイプライン コンポーネントは、2 種類の方法でエラーを報告します。  
  
-   .NET ベースのコンポーネントの場合は、例外をスローします。  
  
-   COM ベースのコンポーネントで設定して、 **ErrorInfo**オブジェクトと HRESULT エラーを返します。  
  
## <a name="reporting-errors-from-net-pipeline-components"></a>.NET パイプライン コンポーネントからのエラーの報告  
 .NET ベースのパイプライン コンポーネントは、エラーを報告するために、例外をスローしてエラーの説明を通知する必要があります。 エラーをスローしたコンポーネントの名前を報告するには、設定、**ソース**のプロパティ、**例外**オブジェクト。  
  
 メッセージング エンジンを使用して、**メッセージ**と**ソース**のプロパティ、**例外**エラーを報告するオブジェクト。 次のメッセージがイベント ログに書き込まれます。  
  
 "エラーが発生しましたを実行する、[受信 (& a) #124; 送信] パイプライン:\<パイプライン名 > ソース:\<元 > [受信場所 (&) #124 です。送信ポート:]\<場所 (&) #124 ですポート名 > 理由:\<メッセージ > です。"。  
  
## <a name="reporting-errors-from-com-pipeline-components"></a>COM パイプライン コンポーネントからのエラーの報告  
 COM ベースのパイプライン コンポーネントは、エラーを報告するために以下のアクションを実行します。  
  
1.  パイプライン コンポーネント セット、 **IErrorInfo**オブジェクトを呼び出して、 **SetErrorInfo**メソッドです。  
  
2.  パイプライン コンポーネントは、HRESULT エラーをメッセージング エンジンに返します。  
  
 メッセージング エンジンを使用して、 **GetSource**と**GetDescription**のプロパティ、 **IErrorInfo**エラーを報告するオブジェクト。 送信元が設定されていない場合は、コンポーネントの名前を使用します。 説明設定されていないか、全体場合**ErrorInfo**オブジェクトが設定されていない、返された HRESULT を報告、説明の代わりにします。 次のメッセージがイベント ログに書き込まれます。  
  
 "エラーが発生しましたを実行する、[受信 (& a) #124; 送信] パイプライン:\<パイプライン名 > ソース: \<GetSource > [受信場所 (&) #124 です。送信ポート:]\<場所 (&) #124 ですポート名 > 理由: \<GetDescription または HRESULT > です。"。  
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)