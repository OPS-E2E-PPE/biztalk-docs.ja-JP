---
title: FRR NAK ハンドラー サンプルの動作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009cb0c3dffce5f88c72207866f6778e3deb7b28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209202"
---
# <a name="how-the-frr-nak-handler-sample-works"></a><span data-ttu-id="b4890-102">FRR NAK ハンドラーのサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="b4890-102">How the FRR NAK Handler Sample Works</span></span>
<span data-ttu-id="b4890-103">サンプル FRR NAK カスタム ハンドラーは、FIN 対応調整 (FRR) オーケストレーションとメッセージ修復オーケストレーション間の媒介として機能します。</span><span class="sxs-lookup"><span data-stu-id="b4890-103">The sample FRR NAK custom handler serves as an intermediary between the FIN Response Reconciliation (FRR) orchestration and the message-repair orchestration.</span></span> <span data-ttu-id="b4890-104">FRR オーケストレーションでは、SWIFT ネットワークは、メッセージを受信しようとしました。 ときに発生したエラーを識別します。</span><span class="sxs-lookup"><span data-stu-id="b4890-104">The FRR orchestration identifies the error that occurred when the SWIFT network attempted to receive the message.</span></span> <span data-ttu-id="b4890-105">FRR オーケストレーションの出力は、エラー オブジェクトを 1 つの部分から成るメッセージです。</span><span class="sxs-lookup"><span data-stu-id="b4890-105">The output of the FRR orchestration is a one-part message with an error object.</span></span> <span data-ttu-id="b4890-106">FRR NAK カスタム ハンドラーは、そのメッセージをメッセージ修復オーケストレーションによって取り出されるメッセージの有効化して発生したエラーを示すエラー部分を含む、2 つの部分のメッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="b4890-106">The FRR NAK custom handler transforms that message into a two-part message, with an error part that indicates the error that occurred, enabling the message to be picked up by the message-repair orchestration.</span></span> <span data-ttu-id="b4890-107">メッセージ修復オーケストレーションでメッセージを開くと、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、エラーの確認、同様に、メッセージを修復して再送信することができますができるように[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAA を再送信できます。</span><span class="sxs-lookup"><span data-stu-id="b4890-107">The message-repair orchestration opens the message in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form that enables you to find out what the error was, repair the message accordingly, and resubmit it so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can resend it to SAA.</span></span>  
  
 <span data-ttu-id="b4890-108">次の手順では、FRR NAK カスタム ハンドラーは、SWIFT ネットワークを正常に受信できません。 メッセージを処理するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b4890-108">The following steps occur when the FRR NAK custom handler processes a message that the SWIFT network could not successfully receive:</span></span>  
  
1.  <span data-ttu-id="b4890-109">FRR オーケストレーションには、MTS21_FIN_ACKNAK NAK メッセージに失敗したメッセージが関連付けられますが後、RepairSWIFTRejectedMessage オーケストレーション (カスタム ハンドラー) は、MessageBox から元のメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="b4890-109">After the FRR orchestration has correlated the failed message to the MTS21_FIN_ACKNAK NAK message, the RepairSWIFTRejectedMessage orchestration (the custom handler) picks up the original message from the MessageBox.</span></span> <span data-ttu-id="b4890-110">これはため A4SWIFT_FRRFailed でフィルター処理するため = = True および A4SWIFT_SendingServiceType"A4SWIFT_FrrService"を = です。</span><span class="sxs-lookup"><span data-stu-id="b4890-110">It does so because it filters on A4SWIFT_FRRFailed==True and A4SWIFT_SendingServiceType="A4SWIFT_FrrService".</span></span>  
  
2.  <span data-ttu-id="b4890-111">元のメッセージを相互に関連付けて FRR MTS21_FIN_ACKNAK NAK メッセージ、カスタム ハンドラーは選択されません。</span><span class="sxs-lookup"><span data-stu-id="b4890-111">The custom handler does not pick up the MTS21_FIN_ACKNAK NAK message that FRR correlated to the original message.</span></span> <span data-ttu-id="b4890-112">代わりに、エラー コレクション オブジェクトを作成、BRE の検証エラーを示す A4SWIFT_FRRFailedReason プロパティを通知し、元のメッセージに追加の設定。</span><span class="sxs-lookup"><span data-stu-id="b4890-112">Instead, it creates an error collection object, populates it with a BRE validation error that indicates what the A4SWIFT_FRRFailedReason property was, and adds it to the original message.</span></span> <span data-ttu-id="b4890-113">メッセージ修復オーケストレーションは、この 2 つの部分から成るメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="b4890-113">The message-repair orchestration can process this two-part message.</span></span>  
  
3.  <span data-ttu-id="b4890-114">カスタム ハンドラーは、メッセージ修復オーケストレーションによって取り出されるメッセージが発生する次のプロパティを昇格: A4SWIFT_Failed A4SWIFT_SwiftBound を = True、= = = True で、BTS です。操作"A4SWIFT_DASMMarkedAsFailed"を = です。</span><span class="sxs-lookup"><span data-stu-id="b4890-114">The custom handler promotes the following properties to cause the message to be picked up by the message-repair orchestration: A4SWIFT_Failed==True, A4SWIFT_SwiftBound==True, and BTS.Operation="A4SWIFT_DASMMarkedAsFailed".</span></span> <span data-ttu-id="b4890-115">パーツのプロパティの数を 2 に設定し、適切なエラー プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b4890-115">It sets the number of parts property to 2, and sets the appropriate error properties.</span></span>  
  
4.  <span data-ttu-id="b4890-116">、昇格されたプロパティの結果としてメッセージ修復オーケストレーションがメッセージを取得し、RepairSWIFTRejectedMessage オーケストレーションは終了します。</span><span class="sxs-lookup"><span data-stu-id="b4890-116">As a result of the promoted properties, the message-repair orchestration picks up the message, and the RepairSWIFTRejectedMessage orchestration terminates.</span></span>