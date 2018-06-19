---
title: バッチ処理のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, troubleshooting
- troubleshooting, batching
ms.assetid: f47e1a16-47fd-4bd8-8dad-fcdba31a833e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c8413a8022529e6ace56c50d5e6d75267a72e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206306"
---
# <a name="troubleshooting-batching"></a><span data-ttu-id="073f2-102">バッチ処理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="073f2-102">Troubleshooting Batching</span></span>
<span data-ttu-id="073f2-103">関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="073f2-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
## <a name="error-activating-batch"></a><span data-ttu-id="073f2-104">アクティブ化のバッチのエラー</span><span class="sxs-lookup"><span data-stu-id="073f2-104">Error activating batch</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="073f2-105">現象</span><span class="sxs-lookup"><span data-stu-id="073f2-105">Symptom</span></span>  
 <span data-ttu-id="073f2-106">バッチをアクティブにできません。</span><span class="sxs-lookup"><span data-stu-id="073f2-106">Unable to activate a batch.</span></span> <span data-ttu-id="073f2-107">一般的なネットワーク エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="073f2-107">You get a general network error.</span></span>  
  
<span data-ttu-id="073f2-108">**考えられる原因**:[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]再起動されましたが、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーでした。</span><span class="sxs-lookup"><span data-stu-id="073f2-108">**Possible Cause** : [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was restarted, but [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer was not.</span></span>  
  
<span data-ttu-id="073f2-109">**解像度**: 再起動[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="073f2-109">**Resolution** : Restart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a><span data-ttu-id="073f2-110">ターゲットの名前空間が既定ではない場合は、メッセージをバッチ処理されません。</span><span class="sxs-lookup"><span data-stu-id="073f2-110">Messages are not batched when the target namespace is not the default</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="073f2-111">現象</span><span class="sxs-lookup"><span data-stu-id="073f2-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="073f2-112">メッセージのバッチを処理はありません。</span><span class="sxs-lookup"><span data-stu-id="073f2-112"> is not batching messages.</span></span>  
  
<span data-ttu-id="073f2-113">**考えられる原因**: 送信元と送信先のパーティは、同じスキーマの名前空間ではありません。</span><span class="sxs-lookup"><span data-stu-id="073f2-113">**Possible Cause** : Source and destination parties are not in the same schema namespace.</span></span>  
  
<span data-ttu-id="073f2-114">**解像度**: 検証が必要な場合、送信元と送信先のパーティが同じスキーマの名前空間を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="073f2-114">**Resolution** : Source and destination parties must use the same schema namespace if validation is required.</span></span> <span data-ttu-id="073f2-115">送信元と移行先のパーティが同じスキーマの名前空間を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="073f2-115">Ensure the source and destination parties are using the same schema namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073f2-116">参照</span><span class="sxs-lookup"><span data-stu-id="073f2-116">See Also</span></span>  
 [<span data-ttu-id="073f2-117">HL7 のトラブルシューティングと既知の問題</span><span class="sxs-lookup"><span data-stu-id="073f2-117">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)