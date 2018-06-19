---
title: FRR 処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, processing
- FRR, components
- FRR, process flow
ms.assetid: 8b064d18-5ee7-44fd-95d1-9a0d66f1ad1a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2b0d34ccffd2bf09148bcfc5544b38ea5d0033d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208970"
---
# <a name="frr-processing"></a>FRR 処理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 対応調整 (FRR) 機能では関連付けるから元のメッセージの FIN メッセージ SWIFT Alliance アクセス (SAA) から[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA メッセージに応答します。 たびに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを送信元、FRR キャッシュ SWIFT およびにバインドされているすべてのメッセージのコピー処理は失敗していません。 SAA によって返される応答メッセージをメッセージ ボックス データベースを監視します[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、し、キャッシュされたメッセージのコピーに対応するすべての ACK/NAK メッセージを取得します。  
  
 FRR は、関連付け ID のプロパティを比較することによって、送信メッセージと、受信メッセージの間の相関関係を確立します。 FRR は、応答の性質によって、元のメッセージのコピーの昇格させたプロパティを設定し、さらに処理用のメッセージ ボックスに、元のメッセージをルーティングします。  
  
## <a name="frr-components"></a>FRR コンポーネント  
 FRR には、送信および受信のメッセージを監視して、各送信または受信メッセージの比較のために使用する id プロパティを昇格する継続的なプロセス (オーケストレーション) が含まれています。 一連の[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR オーケストレーション、メッセージ内の FRR コンポーネント間でルーティングとコンポーネントが連動[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、および[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA とします。 これらのコンポーネントは、次に示します。  
  
-   FRR バックエンド アプリケーションから元のメッセージを受信場所が表示されます。  
  
-   送信および受信のメッセージを監視して、それらの間の相関関係を確立する FRR オーケストレーションです。  
  
-   元のメッセージを送信するポートの送信、FRR [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SAA にします。  
  
-   BizTalk Adapter for MQSeries を間データ転送を有効にする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SAA (を MQSeries キューを使用)。  
  
-   FRR SAA から FIN 応答メッセージを受信場所が表示されます。  
  
-   セットから特定の種類の関連付けられたメッセージを送信それぞれが、FRR 送信ポートの[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム処理するためのバックエンド アプリケーションにします。  
  
 上記のコンポーネントには、FRR によって昇格されたプロパティが設定されている元のメッセージを処理するバックエンドのカスタム ハンドラーを追加できます。  
  
## <a name="frr-process-flow"></a>FRR プロセス フロー  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]次のプロセスで調整を実行します。  
  
1.  バックエンド アプリケーションに元のメッセージをルーティングする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。  
  
2.  受信場所が、FRR メッセージを受信、関連付けられている受信パイプラインで処理し、BizTalk メッセージ ボックスにルーティングします。  
  
    > [!NOTE]
    >  組み合わせて FRR を使用することができます、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の機能、または個別にします。 メッセージの修復 and New Submission をインストールした場合は、手順 2 の後にメッセージの修復のため、システムを構成できます。 メッセージ修復オーケストレーションは、FRR の後続の処理用の BizTalk メッセージ ボックスに、修復/確認/承認メッセージをルーティングします。  
  
3.  メッセージ ボックス データベース内のメッセージが SWIFT にバインドされているし、検証が成功[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR オーケストレーションのインスタンスをアクティブにします。 オーケストレーションは、送信メッセージのコピーを保持します。 すべての着信応答への送信メッセージを照合できるようにし、SAA からの応答をアクティブ化された状態で待機します。 このオーケストレーションのインスタンスは、その特定の送信メッセージとそのメッセージを相関応答にのみ処理します。 でも、同じ型の他のメッセージは、別のオーケストレーションのインスタンスによって処理されます。  
  
4.  同時を[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR オーケストレーション インスタンスをアクティブに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA にメッセージを送信する送信ポートにメッセージをルーティングします。 送信パイプラインは、メッセージ id プロパティと MQSeries によって処理に必要なプロパティを昇格させます。 MQSeries の BizTalk アダプターにメッセージを送信します。  
  
5.  BizTalk Adapter for MQSeries は、SAA に該当する MQSeries キューにメッセージを転送します。  
  
6.  SAA に直接ルーティングに直接応答を生成する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 次に、SAA は SWIFT ネットワークに、メッセージをルーティングします。 SWIFT ネットワークにルーティング SAA に送信する他の応答を生成する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 SAA は、元のメッセージのメッセージ id 値を FIN 応答メッセージの関連付けトークン プロパティを設定します。  
  
7.  BizTalk Adapter for MQSeries を介して FIN 応答にバックアップ SAA トランスポート[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。  
  
8.  受信場所が、FRR 応答を受信し、FRR を介してメッセージをルーティングする応答の相関トークンを処理する受信パイプラインです。 BizTalk メッセージ ボックスで、応答を配置します。  
  
9. FRR オーケストレーション インスタンスをコピー元のメッセージのメッセージの ID プロパティに等しく関連付けトークンを持つ MessageBox からメッセージを取得します。  
  
10. 応答が、元のメッセージが SAA/SWIFT によって正常に処理されたことを示している場合、FRR オーケストレーション インスタンスを False に、元のメッセージのコピーの A4SWIFT_Failed 昇格させたプロパティを設定し、BTS を設定します。適切な値にプロパティを操作します。  
  
11. 元のメッセージが正常に処理されていない場合 SAA/SWIFT によって、FRR オーケストレーション インスタンスは、BTS を設定します。操作のプロパティを適切な値に、A4SWIFT_Failed を True に設定し、失敗の理由を A4SWIFT_FRRFailedReason 昇格させたプロパティを設定し、修復のため、メッセージを指定します。  
  
12. FRR オーケストレーション インスタンスは、応答メッセージを破棄し、(昇格させたプロパティが応答を示す) のメッセージ ボックスに、コピー元のメッセージをルーティングします。  
  
13. FRR 送信ポートの 1 つは、昇格させたプロパティを持つ元のメッセージのコピーを 1 つまたは複数のカスタム ハンドラー ピックアップへの応答をルーティングするを設定します。  
  
14. カスタム ハンドラーまたはハンドラーをサブスクライブし、取得した場合、バックエンド アプリケーションに必要な元のメッセージのコピーを処理します。