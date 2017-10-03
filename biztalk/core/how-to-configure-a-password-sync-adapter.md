---
title: "パスワード同期アダプターを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f0be0146e905ef291942bd30adc111eff89e989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-password-sync-adapter"></a><span data-ttu-id="c0450-102">パスワード同期アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c0450-102">How to Configure a Password Sync Adapter</span></span>
<span data-ttu-id="c0450-103">パスワード同期アダプターの作成が完了した後で、作成したアダプターをシステム上に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0450-103">After you have finished creating your password sync adapter, you must load your adapter on to a system.</span></span> <span data-ttu-id="c0450-104">また、エンタープライズ シングル サインオン (ENTSSO) および構成ストアに、アプリケーションがパスワード同期アダプターであることを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0450-104">Additionally, you must inform Enterprise Single Sign-On (ENTSSO) and the configuration store that your application is a password sync adapter.</span></span> <span data-ttu-id="c0450-105">セキュリティのための構成ストアに登録する必要があります。 アダプターは、パスワードおよびその他の資格情報に更新プログラムが要求されます。</span><span class="sxs-lookup"><span data-stu-id="c0450-105">You must register with the configuration store for security purposes: your adapter will request updates to passwords and other credentials.</span></span> <span data-ttu-id="c0450-106">このため、特定のアダプターがこの権限を要求する許可を取得していることを ENTSSO が認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0450-106">Therefore, ENTSSO must know that a given adapter is allowed to ask for such permissions.</span></span>  
  
### <a name="to-configure-a-password-sync-adapter"></a><span data-ttu-id="c0450-107">パスワード同期アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="c0450-107">To configure a password sync adapter</span></span>  
  
1.  <span data-ttu-id="c0450-108">ssops ツールを使用して、構成ストアにアダプターを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0450-108">Create your adapter with the configuration store using the ssops tool.</span></span>  
  
     <span data-ttu-id="c0450-109">ssops を使用して、構成データベースに XML 構成ファイルを読み込みます。データベースには、エンタープライズ シングル サインオンに対するアプリケーションが記述されます。</span><span class="sxs-lookup"><span data-stu-id="c0450-109">Using ssops, you load an XML configuration file into the configuration database that describes your application to Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="c0450-110">アダプターと構成データベースを共に作成すると、`ISSOPSAdmin.SetAdapterProperties` のアダプター情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c0450-110">After you create the adapter with the config database, you can modify the adapter information with `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
     <span data-ttu-id="c0450-111">2 つの方法は似ていますが、`SetAdapterProperties` では、構成情報が変更されたときにメッセージがアダプターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c0450-111">While the two methods are similar, `SetAdapterProperties` sends a message to the adapter when the configuration information changes.</span></span>  
  
3.  <span data-ttu-id="c0450-112">アダプターを削除するには、ISSOAdmin.DeleteApplication を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0450-112">To delete an adapter, use ISSOAdmin.DeleteApplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0450-113">参照</span><span class="sxs-lookup"><span data-stu-id="c0450-113">See Also</span></span>  
 [<span data-ttu-id="c0450-114">パスワードの同期</span><span class="sxs-lookup"><span data-stu-id="c0450-114">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)