---
title: アダプター ハンドラーを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e26caf02978006040e52ed3c62e520f51362e2c4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969864"
---
# <a name="how-to-create-an-adapter-handler"></a><span data-ttu-id="3b319-102">アダプター ハンドラーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="3b319-102">How to Create an Adapter Handler</span></span>
<span data-ttu-id="3b319-103">BizTalk Server 管理コンソールを使用して、送信または受信のアダプター ハンドラーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3b319-103">You can create a send or receive adapter handler by using the BizTalk Server Administration Console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b319-104">アダプター ハンドラーを作成するには、シングル サインオン管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b319-104">You must be a member of the Single Sign-On Administrators group to create an adapter handler.</span></span>  
  
### <a name="to-create-an-adapter-handler"></a><span data-ttu-id="3b319-105">アダプター ハンドラーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3b319-105">To create an adapter handler</span></span>  
  
1.  <span data-ttu-id="3b319-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="3b319-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="3b319-107">展開したアダプターの一覧で、対象のように、送信を追加または受信ハンドラーをポイントし、アダプターを右クリックして**新規**、クリックして**送信ハンドラー**送信ハンドラーを作成または、をクリックする**受信ハンドラー**受信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b319-107">In the expanded adapter list, right-click the adapter for which you would like to add a send or receive handler, point to **New**, and then click **Send Handler** to create a send handler or click **Receive Handler** to create a receive handler.</span></span>  
  
3.  <span data-ttu-id="3b319-108">**\<ホスト名\>プロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、ホストを選択、アダプターハンドラーは、関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="3b319-108">In the **\<host name\> Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the adapter handler will be associated.</span></span>  
  
4.  <span data-ttu-id="3b319-109">アダプターの送信ハンドラーを作成する場合は、するオプションを選択**しやすいように、既定のハンドラー**このアダプターの既定の送信ハンドラーであるこの必要なかどうかです。</span><span class="sxs-lookup"><span data-stu-id="3b319-109">If you are creating an adapter send handler, select the option to **Make this the default handler** if you would like for this to be the default send handler for this adapter.</span></span>  
  
5.  <span data-ttu-id="3b319-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b319-110">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b319-111">参照</span><span class="sxs-lookup"><span data-stu-id="3b319-111">See Also</span></span>  
 [<span data-ttu-id="3b319-112">アダプター ハンドラーの作成と削除</span><span class="sxs-lookup"><span data-stu-id="3b319-112">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)