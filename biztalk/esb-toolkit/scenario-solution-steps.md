---
title: ソリューションのシナリオの手順 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77751c15-9b67-4587-8bc8-2be65f13d339
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd2f7623487670041ed2684fc096b669eaef1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394022"
---
# <a name="scenario-solution-steps"></a>ソリューションのシナリオの手順
ESB 例外管理フレームワークは、請求書メッセージに、処理中にエラーが発生する無効なデータが含まれている場合では、このトピックで前述したように、例外を処理するためのシンプルなソリューションを提供します。 以下は、1 つの方法がかかる場合があります。  
  
1.  チームの開発者に、Microsoft BizTalk に基づいて最後に配置された、財務報告アプリケーションに対する責任を割り当てます。  
  
2.  ESB 管理ポータルで新しい ESB エラー メッセージが到着します。メッセージでは、財務報告の BizTalk アプリケーション内のオーケストレーションでのデータ整合性の問題を示します。  
  
3.  管理者やオペレーターが、新しい例外の開発者に通知します。 または、開発者が、例外が発生したときに自動で通知に登録します。 次の理由の 1 つこの通知が発生する可能性があります。  
  
    -   例外でイベントに基づくビジネス アクティビティ監視 (BAM) 定義済みのしきい値を超えたために発生します。  
  
    -   これは、BizTalk サブスクリプションは、特定のアプリケーション、サービス、スコープ、および開発者に、例外を転送するエラー コードに存在するために発生します。  
  
4.  開発者は、エラー メッセージ、個別のオーケストレーションのメッセージと、永続化されたコンテキスト プロパティの値を調べます。 開発者は、ESB 管理ポータル、または BizTalk サブスクリプションによる Microsoft Outlook を使用して、この情報を表示できます。  
  
5.  開発者は、これは、一般的なエラーであることを決定します。 必要になります手動介入し、修正によって、システムを再送信を続けて、財務チーム。  
  
6.  開発者は、作成し、特定のアプリケーションおよび例外の種類をサブスクライブする独立した BizTalk オーケストレーション プロジェクトを展開します。  
  
7.  オーケストレーション プロジェクトで、ESB エラー メッセージから無効なメッセージを取得、修正のために財務チームにメッセージを送信、オーケストレーションに修正されたメッセージを相関し、再送信します。  
  
8.  1 週間後、開発者は、検出を無効なメッセージのアプリケーション例外の傾向が大幅に短縮されましたので、このソリューションがデプロイされた ESB 管理ポータルに移動します。