---
title: "JD Edwards EnterpriseOne の BizTalk アダプターの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, JD Edwards EnterpriseOne adapters
- JD Edwards EnterpriseOne adapters, installing
- adapters [JD Edwards EnterpriseOne adapters], installing
ms.assetid: baecebcd-c324-40aa-bacf-876f45b6c37f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ab141d8f3227c12abd9a790bc82fa8f9ada3ae8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="7d9a1-102">BizTalk Adapter for JD Edwards EnterpriseOne の追加</span><span class="sxs-lookup"><span data-stu-id="7d9a1-102">Adding BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="7d9a1-103">Microsoft BizTalk Adapter for J.D.Edwards EnterpriseOne には、Receive Handler フォルダーと Send Handler フォルダーの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-103">Microsoft BizTalk Adapter for J.D.Edwards EnterpriseOne contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="7d9a1-104">これらのフォルダーには、BizTalkServerApplication が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-104">The folders contain BizTalkServerApplication.</span></span> <span data-ttu-id="7d9a1-105">BizTalk Adapter for J.D.Edwards EnterpriseOne は、BizTalk Server と共にインプロセスで実行され、分離ホスト プロセスでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-105">BizTalk Adapter for J.D.Edwards EnterpriseOne is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
### <a name="to-add-the-adapter-to-biztalk-server"></a><span data-ttu-id="7d9a1-106">アダプターを BizTalk Server に追加するには</span><span class="sxs-lookup"><span data-stu-id="7d9a1-106">To add the adapter to BizTalk Server</span></span>  
  
1.  <span data-ttu-id="7d9a1-107">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-107">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7d9a1-108">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**です。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-108">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="7d9a1-109">右クリック**アダプター**、指す**新規**、 をクリック**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-109">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="7d9a1-110">アダプターの名前を入力します。たとえば、`JDEEnterpriseOne`です。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-110">Type a name for the adapter; for example, `JDEEnterpriseOne`.</span></span>  
  
5.  <span data-ttu-id="7d9a1-111">選択**JDEEnterpriseOne**から、**アダプター**ボックスの一覧し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7d9a1-111">Select **JDEEnterpriseOne** from the **Adapter** list, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d9a1-112">参照</span><span class="sxs-lookup"><span data-stu-id="7d9a1-112">See Also</span></span>  
 [<span data-ttu-id="7d9a1-113">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="7d9a1-113">Developing Applications</span></span>](../core/developing-applications2.md)