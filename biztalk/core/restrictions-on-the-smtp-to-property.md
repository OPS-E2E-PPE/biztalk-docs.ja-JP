---
title: "SMTP の To プロパティに関する制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: c876d30e-44ab-462d-8c98-64416ed6dd1f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b59495ac94b3591801101607533eb9c7dba158fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-smtp-to-property"></a><span data-ttu-id="0f927-102">SMTP の To プロパティに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="0f927-102">Restrictions on the SMTP To Property</span></span>
<span data-ttu-id="0f927-103">**に**プロパティは、メッセージの受信者の SMTP アドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="0f927-103">The **To** property is a string that specifies the SMTP address of the recipient of the message.</span></span> <span data-ttu-id="0f927-104">SMTP サーバーでサポートされている区切り記号を使用して、複数のアドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0f927-104">You can list several addresses with a separator that SMTP server supports.</span></span>  
  
 <span data-ttu-id="0f927-105">SMTP アドレスの形式に固有の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="0f927-105">There are no specific restrictions for the format of an SMTP address.</span></span> <span data-ttu-id="0f927-106">したがって、アダプタは SMTP サーバーでサポートされているすべての形式を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0f927-106">This means that the adapter will accept any format that an SMTP server supports.</span></span> <span data-ttu-id="0f927-107">ユーザーが有効でないアドレスを指定すると、送信操作は失敗し、SMTP 送信アダプタによってエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="0f927-107">If a user provides addresses that are not valid, the send operation will fail and the SMTP send adapter will report an error.</span></span>  
  
 <span data-ttu-id="0f927-108">このプロパティの唯一の制限は、プロパティが空でなく、サイズが 256 文字を超えないようにする必要があることです。</span><span class="sxs-lookup"><span data-stu-id="0f927-108">The only restrictions for this property are that it must not be empty and its size must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f927-109">参照</span><span class="sxs-lookup"><span data-stu-id="0f927-109">See Also</span></span>  
 [<span data-ttu-id="0f927-110">SMTP アダプタの構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="0f927-110">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)