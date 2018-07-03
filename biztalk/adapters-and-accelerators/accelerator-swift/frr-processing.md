---
title: FRR 処理 |Microsoft Docs
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
ms.openlocfilehash: 30c343d214a97895e90bae2bc3a041180c0cc8e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987011"
---
# <a name="frr-processing"></a>FRR 処理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 応答の調整 (FRR) 機能から元のメッセージを FIN メッセージ SWIFT Alliance アクセス (SAA) からを相関付ける[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA メッセージに応答します。 たびに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを送信元、FRR キャッシュ SWIFT およびにバインドされているすべてのメッセージのコピーが、処理できませんでしたが。 SAA にによって返される応答メッセージのメッセージ ボックス データベースを監視します[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]とキャッシュされたメッセージのコピーに対応するすべての ACK/NAK メッセージを取得します。  

 FRR は、関連付け ID のプロパティを比較することによって、送信メッセージと受信メッセージの間の相関関係を確立します。 FRR は、応答の性質に応じて、元のメッセージのコピーの昇格させたプロパティを設定し、さらに処理するため、メッセージ ボックスに、元のメッセージをルーティングします。  

## <a name="frr-components"></a>FRR コンポーネント  
 FRR には送信および受信のメッセージを監視し、各送信または受信メッセージの比較のために使用する id プロパティを昇格させます。 継続的なプロセス (オーケストレーション) が含まれます。 一連の[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]コンポーネントがメッセージ内の FRR コンポーネント間のルーティング、FRR オーケストレーションと連携[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、および[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA とします。 これらのコンポーネントは、以下に示します。  

- FRR、バックエンド アプリケーションから元のメッセージを受信場所が表示されます。  

- FRR オーケストレーション送信および受信のメッセージを監視し、それらの間の相関関係を確立します。  

- FRR 送信ポートから元のメッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAA にします。  

- BizTalk Adapter for MQSeries の間でデータ転送できるようにする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SAA (を MQSeries キューを使用)。  

- FRR SAA から FIN 応答メッセージを受信場所が表示されます。  

- 一連の FRR 送信ポートから特定の種類の関連付けられたメッセージを送信各[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム処理をバックエンド アプリケーションにします。  

  上記のコンポーネントに FRR で昇格させたプロパティが設定されている元のメッセージを処理するバック エンドのカスタム ハンドラーを追加できます。  

## <a name="frr-process-flow"></a>FRR 処理フロー  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 次のプロセスで調整を実行します。  

1. バックエンド アプリケーションが元のメッセージをルーティング[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。  

2. FRR 受信場所がメッセージを受信、関連付けられている受信パイプラインで処理し、BizTalk メッセージ ボックスにルーティングします。  

   > [!NOTE]
   >  FRR と組み合わせて使用することができます、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の機能も、個別にします。 メッセージの修復 and New Submission をインストールした場合は、手順 2 の後にメッセージ修復のため、システムを構成できます。 メッセージ修復オーケストレーションは、後続の FRR 処理用の BizTalk メッセージ ボックスに、修復/検証/承認メッセージをルーティングします。  

3. メッセージ ボックス データベース内のメッセージは、SWIFT にバインドされているし、検証に合格した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR オーケストレーションのインスタンスをアクティブにします。 オーケストレーションでは、送信メッセージのコピーを保持します。 送信されるメッセージの受信応答に一致することができるようにし、SAA からの応答をアクティブ化された状態で待機します。 このオーケストレーションのインスタンスは、その特定の送信メッセージとそのメッセージを相関応答にのみ処理します。 でも、同じ型でのその他のすべてのメッセージは、別のオーケストレーションのインスタンスによって処理されます。  

4. 同時にされる[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR オーケストレーション インスタンスをアクティブに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA にメッセージを送信する送信ポートにメッセージをルーティングします。 送信パイプラインは、メッセージ id プロパティと MQSeries によって処理に必要なプロパティを昇格します。 MQSeries の BizTalk アダプターにメッセージを送信します。  

5. BizTalk Adapter for MQSeries は、SAA に該当する MQSeries キューにメッセージを転送します。  

6. SAA に直接ルーティングにすぐに応答を生成する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 SAA は、SWIFT ネットワークにメッセージをルーティングします。 SWIFT ネットワークは、ルーティングに SAA に送信する他の応答を生成します。[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 SAA は、FIN 応答メッセージの関連付けトークン プロパティを元のメッセージのメッセージ id の値に設定します。  

7. BizTalk Adapter for MQSeries を FIN 応答を返信 SAA トランスポート[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。  

8. として FRR 受信場所、応答を受信し、として FRR を介してメッセージをルーティング、応答の関連付けトークンを処理するパイプラインを受信します。 BizTalk メッセージ ボックスで、応答を配置します。  

9. FRR オーケストレーションのインスタンスは、コピー元のメッセージのメッセージの ID プロパティと同じ関連付けトークンを含むメッセージ ボックス データベースからすべてのメッセージを取得します。  

10. 応答は、元のメッセージが SAA/SWIFT によって正常に処理されたことを示している場合、FRR オーケストレーションのインスタンスを False に、元のメッセージのコピーの A4SWIFT_Failed 昇格させたプロパティを設定し、BTS を設定します。適切な値のプロパティを操作します。  

11. 元のメッセージが SAA/SWIFT によって正常に処理されなかった場合、FRR オーケストレーション インスタンスは、BTS を設定します。操作のプロパティを適切な値を A4SWIFT_Failed を True に設定し、失敗の理由に A4SWIFT_FRRFailedReason 昇格させたプロパティを設定して修復のためのメッセージを指定します。  

12. FRR オーケストレーションのインスタンスは、応答メッセージを破棄し、(昇格させたプロパティが応答を示す) を持つメッセージ ボックスに、コピー元のメッセージをルーティングします。  

13. FRR 送信ポートの 1 つは、昇格させたプロパティの元のメッセージのコピーを 1 つまたは複数のカスタム ハンドラー ピックアップへの応答のルーティングを設定します。  

14. カスタム ハンドラーまたはハンドラーをサブスクライブしている、取得、およびバックエンド アプリケーションに必要な元のメッセージのコピーを処理します。
