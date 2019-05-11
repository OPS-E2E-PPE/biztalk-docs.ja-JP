---
title: SMTP の To プロパティに関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: c876d30e-44ab-462d-8c98-64416ed6dd1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75539b7bcd9feb1e66695361a1a208b12eda812
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399110"
---
# <a name="restrictions-on-the-smtp-to-property"></a><span data-ttu-id="498fe-102">SMTP の To プロパティに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="498fe-102">Restrictions on the SMTP To Property</span></span>
<span data-ttu-id="498fe-103">**に**プロパティは、メッセージの受信者の SMTP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="498fe-103">The **To** property is a string that specifies the SMTP address of the recipient of the message.</span></span> <span data-ttu-id="498fe-104">SMTP サーバーがサポートする区切り記号では、いくつかのアドレスを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="498fe-104">You can list several addresses with a separator that SMTP server supports.</span></span>  
  
 <span data-ttu-id="498fe-105">SMTP アドレスの形式については、特定の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="498fe-105">There are no specific restrictions for the format of an SMTP address.</span></span> <span data-ttu-id="498fe-106">これは、アダプターが SMTP サーバーをサポートする任意の形式を受け入れることを意味します。</span><span class="sxs-lookup"><span data-stu-id="498fe-106">This means that the adapter will accept any format that an SMTP server supports.</span></span> <span data-ttu-id="498fe-107">ユーザーは、無効なアドレスを提供する場合は、送信操作は失敗し、SMTP 送信アダプターはエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="498fe-107">If a user provides addresses that are not valid, the send operation will fail and the SMTP send adapter will report an error.</span></span>  
  
 <span data-ttu-id="498fe-108">このプロパティの唯一の制限は、空を認めないし、そのサイズは 256 文字を超えないことです。</span><span class="sxs-lookup"><span data-stu-id="498fe-108">The only restrictions for this property are that it must not be empty and its size must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="498fe-109">参照</span><span class="sxs-lookup"><span data-stu-id="498fe-109">See Also</span></span>  
 [<span data-ttu-id="498fe-110">SMTP アダプター構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="498fe-110">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)