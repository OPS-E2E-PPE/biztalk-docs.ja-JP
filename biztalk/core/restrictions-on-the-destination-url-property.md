---
title: 送信先 URL のプロパティに関する制限事項 |Microsoft ドキュメント
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
ms.openlocfilehash: 9f7966fccca324a1453f0ea84e79cd7d9d3d55ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25972072"
---
# <a name="restrictions-on-the-destination-url-property"></a><span data-ttu-id="f5756-102">送信先 URL のプロパティに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="f5756-102">Restrictions on the Destination URL Property</span></span>
<span data-ttu-id="f5756-103">送信先 URL とは、HTTP プロトコルを使用して送信するメッセージの送信先となる HTTP サーバーのアドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="f5756-103">The destination URL is a string that specifies the address of the HTTP server where you want to send messages using the HTTP protocol.</span></span>  
  
 <span data-ttu-id="f5756-104">送信先 URL のプロパティには、次の規則および制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5756-104">The following rules and restrictions apply to the destination URL property:</span></span>  
  
-   <span data-ttu-id="f5756-105">送信先 URL のプロパティは、次の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5756-105">You must always specify the destination URL property in the following format:</span></span>  
  
     <span data-ttu-id="f5756-106">http [s]://\<ホスト\>[:\<ポート\>] [/\<パス\>[/\<ファイル\>[?\<クエリ文字列\>]]</span><span class="sxs-lookup"><span data-stu-id="f5756-106">http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]</span></span>  
  
-   <span data-ttu-id="f5756-107">文字列全体は、URI でエンコードできますが、しなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="f5756-107">The whole string may or may not be URI encoded.</span></span>  
  
-   <span data-ttu-id="f5756-108">クエリ文字列を除き、文字列全体には、次の文字を含めることはできません: \< \> : \ &#124; "しますか?</span><span class="sxs-lookup"><span data-stu-id="f5756-108">The whole string, except the query string, cannot contain any of the following characters: \< \> : \ &#124; " ?</span></span> <span data-ttu-id="f5756-109">\*.</span><span class="sxs-lookup"><span data-stu-id="f5756-109">\*.</span></span>  
  
-   <span data-ttu-id="f5756-110">このプロパティは区別されません。</span><span class="sxs-lookup"><span data-stu-id="f5756-110">The property is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="f5756-111">この文字列の長さは 256 文字以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5756-111">The length of the string must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5756-112">参照</span><span class="sxs-lookup"><span data-stu-id="f5756-112">See Also</span></span>  
 [<span data-ttu-id="f5756-113">HTTP 送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="f5756-113">Configuring an HTTP Send Port</span></span>](../core/configuring-an-http-send-port.md)