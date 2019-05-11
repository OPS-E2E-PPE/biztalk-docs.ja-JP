---
title: BizTalk ESB Toolkit メッセージ ライフ サイクル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26db3a32cc31f417d518b2eb8663f2da3ba5e8ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392080"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a>BizTalk ESB Toolkit メッセージ ライフ サイクル
外部システムから開始され、最終的な宛先に到達する ESB を走査するメッセージのライフ サイクルを次に示します。  

1. 傾斜では、メッセージを受信します。 送信のパーティまたはクライアントによって、メッセージは可能性があります。 またはメッセージの処理命令を定義する旅行プランを含めることはできません。  

2. ESB パイプライン コンポーネントをコピー、旅行プラン (SOAP ヘッダーに存在する) 場合、メッセージのコンテキストに昇格させたプロパティとして。 スケジュールなし、メッセージを受信する場合は、メッセージの内容またはコンテキストに応じて、データベースから適切な旅行プランを選択し、メッセージのコンテキストに旅行プランをコピーする特定のパイプライン コンポーネントを構成できます。 メッセージの有効期間中は、メッセージ コンテキスト内で、スケジュールが維持されます。  

3. パイプラインでは、旅行プランが評価され、メッセージ ベースのスケジュール サービスがメッセージを処理できます。 これらのスケジュール サービスは、メッセージを変換またはルーティング エンドポイントの構成可能性があります。  

4. メッセージは、Microsoft BizTalk Server メッセージ ボックス データベースに発行されます。  

5. BizTalk Server では、1 つまたは複数のサブスクライバーのメッセージとキューの昇格させたプロパティ、メッセージを評価します。  

6. サブスクライバーでは、BizTalk Server の一般的なメカニズムを使用してメッセージを処理します。 サブスクライバーには、次のいずれかを指定できます。  

   -   直接バインドで構成されているフィルターを使用して BizTalk Server オーケストレーションの受信ポート  

   -   動的な BizTalk Server は、ESB を導入とも呼ばれますポートを送信します。 旅行プランは、メッセージの処理を続行するポートを構成する方法を決定します。  

   スケジュール オンランプ入り口で到着したメッセージを代わりに、BizTalk Server オーケストレーションが ESB 処理のため、メッセージ ボックスのメッセージを発行することもできます。  

7. メッセージが BizTalk Server オーケストレーション内で作成されます。  

8. メッセージのコンテキストには、ESB 行程が設定されます。  

9. メッセージ ボックス データベースに直接バインドされたポートを通じてメッセージが発行されます。
