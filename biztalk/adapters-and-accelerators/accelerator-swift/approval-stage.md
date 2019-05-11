---
title: 承認ステージ |Microsoft Docs
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
ms.openlocfilehash: de1010d70d407468247f56afe26256d420204123
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378685"
---
# <a name="approval-stage"></a><span data-ttu-id="a455e-102">承認ステージ</span><span class="sxs-lookup"><span data-stu-id="a455e-102">Approval Stage</span></span>
<span data-ttu-id="a455e-103">まず、メッセージが署名され、承認のため送信、承認チェーンの各承認者レビューし、スタックへのデジタル署名の追加、メッセージを副署名します。</span><span class="sxs-lookup"><span data-stu-id="a455e-103">After the message is first signed and submitted for approval, each approver in the approval chain reviews and countersigns the message, adding his or her digital signature to the stack.</span></span> <span data-ttu-id="a455e-104">承認者を確認し、メッセージを副署名のみできます。</span><span class="sxs-lookup"><span data-stu-id="a455e-104">Approvers can only review and countersign the message.</span></span> <span data-ttu-id="a455e-105">デジタル署名のスタックを損なうことがなく変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a455e-105">They cannot change it without breaking the digital signature stack.</span></span>