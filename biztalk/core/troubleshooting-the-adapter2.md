---
title: "トラブルシューティング、Adapter2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991278813d2183795239d1a75c08e474b2f8159a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="16b28-102">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="16b28-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="16b28-103">このトピックでは、Microsoft BizTalk Adapter for PeopleSoft Enterprise の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="16b28-103">This topic contains information to help you identify and resolve issues that you might experience while you are using Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="cannot-use-wildcard-characters-in-send-port-properties"></a><span data-ttu-id="16b28-104">送信ポートのプロパティにワイルドカード文字を使用できない</span><span class="sxs-lookup"><span data-stu-id="16b28-104">Cannot use wildcard characters in send port properties</span></span>  
 <span data-ttu-id="16b28-105">BizTalk Adapter for PeopleSoft Enterprise では、以下の送信ポート プロパティ フィールドにワイルドカード文字を使用できません。</span><span class="sxs-lookup"><span data-stu-id="16b28-105">BizTalk Adapter for PeopleSoft Enterprise does not support using wildcard characters in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="16b28-106">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="16b28-106">Username</span></span>  
  
-   <span data-ttu-id="16b28-107">App Server Path</span><span class="sxs-lookup"><span data-stu-id="16b28-107">App Server Path</span></span>  
  
-   <span data-ttu-id="16b28-108">Java_Home</span><span class="sxs-lookup"><span data-stu-id="16b28-108">Java_Home</span></span>  
  
-   <span data-ttu-id="16b28-109">People JAR Files</span><span class="sxs-lookup"><span data-stu-id="16b28-109">People JAR Files</span></span>  
  
## <a name="getxml-data-assigns-0001-01-01-value-for-null-dates"></a><span data-ttu-id="16b28-110">Get.xml データにより Null の日付に 0001-01-01 値が割り当てられる</span><span class="sxs-lookup"><span data-stu-id="16b28-110">Get.xml data assigns 0001-01-01 value for null dates</span></span>  
 <span data-ttu-id="16b28-111">Get.xml データは、Null の日付に無効な 0001-01-01 値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="16b28-111">Get.xml incorrectly assigns 0001-01-01 value for null dates.</span></span> <span data-ttu-id="16b28-112">0001-01-01 を Null に修正する場合は、BizTalk マッパー ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16b28-112">You must use the BizTalk Mapper tool if you want to replace the 0001-01-01 with null.</span></span>  
  
## <a name="creating-and-updating-properties-with-collections-fails"></a><span data-ttu-id="16b28-113">コレクションでのプロパティの作成および更新に失敗する</span><span class="sxs-lookup"><span data-stu-id="16b28-113">Creating and updating properties with collections fails</span></span>  
 <span data-ttu-id="16b28-114">このアダプターと PeopleSoft version 8.17.02 を併用すると、アダプターは PeopleSoft サーバーからデータを正しく読み取ります。</span><span class="sxs-lookup"><span data-stu-id="16b28-114">When using the Adapter with PeopleSoft version 8.17.02, the Adapter can read data from PeopleSoft server correctly.</span></span> <span data-ttu-id="16b28-115">ただし、コレクションでのプロパティの作成および更新には失敗します。</span><span class="sxs-lookup"><span data-stu-id="16b28-115">However, creating and updating fails for properties with collections.</span></span> <span data-ttu-id="16b28-116">これは、PeopleSoft の既知の問題で、今後の PeopleSoft リリースで修正される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16b28-116">This is a known PeopleSoft issue that may be fixed in a future release of PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b28-117">参照</span><span class="sxs-lookup"><span data-stu-id="16b28-117">See Also</span></span>  
 [<span data-ttu-id="16b28-118">PeopleSoft のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="16b28-118">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)