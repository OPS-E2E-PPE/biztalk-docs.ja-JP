---
title: FRR NAK ハンドラー サンプルのしくみ |Microsoft Docs
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
ms.openlocfilehash: 36b64fb92f130defe6bd7d55ac6ccdc3b7391091
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377434"
---
# <a name="how-the-frr-nak-handler-sample-works"></a><span data-ttu-id="cf6c0-102">FRR NAK ハンドラー サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="cf6c0-102">How the FRR NAK Handler Sample Works</span></span>
<span data-ttu-id="cf6c0-103">FRR NAK のカスタム ハンドラーのサンプルは、FIN 応答の調整 (FRR) オーケストレーションとメッセージ修復オーケストレーション間の媒介として機能します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-103">The sample FRR NAK custom handler serves as an intermediary between the FIN Response Reconciliation (FRR) orchestration and the message-repair orchestration.</span></span> <span data-ttu-id="cf6c0-104">FRR オーケストレーションは、メッセージを受信する SWIFT ネットワークが試行されたときに発生したエラーを識別します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-104">The FRR orchestration identifies the error that occurred when the SWIFT network attempted to receive the message.</span></span> <span data-ttu-id="cf6c0-105">FRR オーケストレーションの出力は、エラー オブジェクトを 1 つのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-105">The output of the FRR orchestration is a one-part message with an error object.</span></span> <span data-ttu-id="cf6c0-106">FRR NAK のカスタム ハンドラーは、そのメッセージをメッセージ修復オーケストレーションによって取得されるメッセージを有効にすると、発生したエラーを示すエラーの部分で、2 つの部分のメッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-106">The FRR NAK custom handler transforms that message into a two-part message, with an error part that indicates the error that occurred, enabling the message to be picked up by the message-repair orchestration.</span></span> <span data-ttu-id="cf6c0-107">メッセージ修復オーケストレーションでメッセージを開くと、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームを使用すると、エラーの確認、メッセージをそれに応じて、修復および再送信するように[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAA を再送信できます。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-107">The message-repair orchestration opens the message in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form that enables you to find out what the error was, repair the message accordingly, and resubmit it so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can resend it to SAA.</span></span>  
  
 <span data-ttu-id="cf6c0-108">次の手順は、FRR NAK のカスタム ハンドラーは、SWIFT ネットワークが正常に受信できなかったメッセージを処理するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-108">The following steps occur when the FRR NAK custom handler processes a message that the SWIFT network could not successfully receive:</span></span>  
  
1.  <span data-ttu-id="cf6c0-109">FRR オーケストレーションが失敗したメッセージを MTS21_FIN_ACKNAK NAK メッセージを相関関係後 RepairSWIFTRejectedMessage オーケストレーション (カスタム ハンドラー) を元のメッセージをメッセージ ボックスから選択します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-109">After the FRR orchestration has correlated the failed message to the MTS21_FIN_ACKNAK NAK message, the RepairSWIFTRejectedMessage orchestration (the custom handler) picks up the original message from the MessageBox.</span></span> <span data-ttu-id="cf6c0-110">これはそのため A4SWIFT_FRRFailed でフィルター処理するため = = True and A4SWIFT_SendingServiceType"A4SWIFT_FrrService"を = です。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-110">It does so because it filters on A4SWIFT_FRRFailed==True and A4SWIFT_SendingServiceType="A4SWIFT_FrrService".</span></span>  
  
2.  <span data-ttu-id="cf6c0-111">元のメッセージに関連する FRR MTS21_FIN_ACKNAK NAK メッセージ、カスタム ハンドラーは選択されません。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-111">The custom handler does not pick up the MTS21_FIN_ACKNAK NAK message that FRR correlated to the original message.</span></span> <span data-ttu-id="cf6c0-112">代わりに、エラーのコレクション オブジェクトを作成し、A4SWIFT_FRRFailedReason プロパティを通知し、元のメッセージに追加することを示す BRE 検証エラーを設定します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-112">Instead, it creates an error collection object, populates it with a BRE validation error that indicates what the A4SWIFT_FRRFailedReason property was, and adds it to the original message.</span></span> <span data-ttu-id="cf6c0-113">メッセージ修復オーケストレーションは、この 2 つの部分のメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-113">The message-repair orchestration can process this two-part message.</span></span>  
  
3.  <span data-ttu-id="cf6c0-114">カスタム ハンドラーは、メッセージがメッセージ修復オーケストレーションによって取得するのには、次のプロパティを昇格します。A4SWIFT_Failed A4SWIFT_SwiftBound を = True、= = = True and BTS します。操作"A4SWIFT_DASMMarkedAsFailed"を = です。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-114">The custom handler promotes the following properties to cause the message to be picked up by the message-repair orchestration: A4SWIFT_Failed==True, A4SWIFT_SwiftBound==True, and BTS.Operation="A4SWIFT_DASMMarkedAsFailed".</span></span> <span data-ttu-id="cf6c0-115">パーツのプロパティの数を 2 に設定し、適切なエラー プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-115">It sets the number of parts property to 2, and sets the appropriate error properties.</span></span>  
  
4.  <span data-ttu-id="cf6c0-116">昇格されたプロパティの結果としてメッセージ修復オーケストレーションがメッセージを取得し、RepairSWIFTRejectedMessage オーケストレーションが終了します。</span><span class="sxs-lookup"><span data-stu-id="cf6c0-116">As a result of the promoted properties, the message-repair orchestration picks up the message, and the RepairSWIFTRejectedMessage orchestration terminates.</span></span>