---
title: 承認ステージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stages, approval
ms.assetid: a3d36956-dabc-4f8c-b61d-d7665289ca76
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4a56d23e2bcfa299c33069172152d1343cb16a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208882"
---
# <a name="approval-stage"></a><span data-ttu-id="49b6d-102">承認ステージ</span><span class="sxs-lookup"><span data-stu-id="49b6d-102">Approval Stage</span></span>
<span data-ttu-id="49b6d-103">メッセージが最初に署名され承認用に送信した後の承認チェーン内の各承認者が確認し、自分のデジタル署名をスタックに追加することをメッセージに副署名します。</span><span class="sxs-lookup"><span data-stu-id="49b6d-103">After the message is first signed and submitted for approval, each approver in the approval chain reviews and countersigns the message, adding his or her digital signature to the stack.</span></span> <span data-ttu-id="49b6d-104">承認者を確認し、メッセージを副署名のみできます。</span><span class="sxs-lookup"><span data-stu-id="49b6d-104">Approvers can only review and countersign the message.</span></span> <span data-ttu-id="49b6d-105">デジタル署名のスタックを分断することがなく変更できません。</span><span class="sxs-lookup"><span data-stu-id="49b6d-105">They cannot change it without breaking the digital signature stack.</span></span>