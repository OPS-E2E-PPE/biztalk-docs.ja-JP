---
title: 送信先 URL のプロパティに関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98220fbc5ec99780d230c46751b903cf34167d8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254876"
---
# <a name="restrictions-on-the-destination-url-property"></a><span data-ttu-id="5905f-102">送信先 URL のプロパティに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="5905f-102">Restrictions on the Destination URL Property</span></span>
<span data-ttu-id="5905f-103">リンク先の URL は、HTTP プロトコルを使用してメッセージを送信する HTTP サーバーのアドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="5905f-103">The destination URL is a string that specifies the address of the HTTP server where you want to send messages using the HTTP protocol.</span></span>  
  
 <span data-ttu-id="5905f-104">送信先 URL のプロパティには、次の規則と制限事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5905f-104">The following rules and restrictions apply to the destination URL property:</span></span>  
  
-   <span data-ttu-id="5905f-105">常に次の形式で送信先 URL のプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5905f-105">You must always specify the destination URL property in the following format:</span></span>  
  
     <span data-ttu-id="5905f-106">http [s]://\<ホスト\>[:\<ポート\>] [/\<パス\>[/\<ファイル\>[でしょうか\<。クエリ文字列\>]]</span><span class="sxs-lookup"><span data-stu-id="5905f-106">http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]</span></span>  
  
-   <span data-ttu-id="5905f-107">文字列全体または可能性がありますいない URI でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5905f-107">The whole string may or may not be URI encoded.</span></span>  
  
-   <span data-ttu-id="5905f-108">クエリ文字列を除く、全体の文字列には、次の文字を含めることはできません: \< \> : \ &#124; "でしょうか。</span><span class="sxs-lookup"><span data-stu-id="5905f-108">The whole string, except the query string, cannot contain any of the following characters: \< \> : \ &#124; " ?</span></span> <span data-ttu-id="5905f-109">\*.</span><span class="sxs-lookup"><span data-stu-id="5905f-109">\*.</span></span>  
  
-   <span data-ttu-id="5905f-110">プロパティは区別されません。</span><span class="sxs-lookup"><span data-stu-id="5905f-110">The property is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="5905f-111">文字列の長さは 256 文字を超えない必要があります。</span><span class="sxs-lookup"><span data-stu-id="5905f-111">The length of the string must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5905f-112">参照</span><span class="sxs-lookup"><span data-stu-id="5905f-112">See Also</span></span>  
 [<span data-ttu-id="5905f-113">HTTP 送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="5905f-113">Configuring an HTTP Send Port</span></span>](../core/configuring-an-http-send-port.md)