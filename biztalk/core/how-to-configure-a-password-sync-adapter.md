---
title: パスワード同期アダプターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82d86947981455cd3ea0d136726a843d385b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386984"
---
# <a name="how-to-configure-a-password-sync-adapter"></a><span data-ttu-id="35f17-102">パスワード同期アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="35f17-102">How to Configure a Password Sync Adapter</span></span>
<span data-ttu-id="35f17-103">パスワード同期アダプターの作成が完了したら、後に、アダプターをシステム上に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f17-103">After you have finished creating your password sync adapter, you must load your adapter on to a system.</span></span> <span data-ttu-id="35f17-104">さらに、必要がありますに通知するエンタープライズ シングル サインオン (ENTSSO) と、構成ストア アプリケーションのパスワード同期アダプター。</span><span class="sxs-lookup"><span data-stu-id="35f17-104">Additionally, you must inform Enterprise Single Sign-On (ENTSSO) and the configuration store that your application is a password sync adapter.</span></span> <span data-ttu-id="35f17-105">セキュリティのため、構成ストアに登録する必要があります。 アダプターはパスワードとその他の資格情報に更新プログラムを要求します。</span><span class="sxs-lookup"><span data-stu-id="35f17-105">You must register with the configuration store for security purposes: your adapter will request updates to passwords and other credentials.</span></span> <span data-ttu-id="35f17-106">そのため、ENTSSO では、このようなアクセス許可を要求する特定のアダプターが許可されているを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f17-106">Therefore, ENTSSO must know that a given adapter is allowed to ask for such permissions.</span></span>  
  
### <a name="to-configure-a-password-sync-adapter"></a><span data-ttu-id="35f17-107">パスワード同期アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="35f17-107">To configure a password sync adapter</span></span>  
  
1.  <span data-ttu-id="35f17-108">Ssops ツールを使用して、構成ストアで、アダプターを作成します。</span><span class="sxs-lookup"><span data-stu-id="35f17-108">Create your adapter with the configuration store using the ssops tool.</span></span>  
  
     <span data-ttu-id="35f17-109">エンタープライズ シングル サインオンにアプリケーションを説明する構成データベースには、ssops し、XML 構成ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="35f17-109">Using ssops, you load an XML configuration file into the configuration database that describes your application to Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="35f17-110">構成データベースで、アダプターを作成した後でアダプターの情報を変更できます`ISSOPSAdmin.SetAdapterProperties`します。</span><span class="sxs-lookup"><span data-stu-id="35f17-110">After you create the adapter with the config database, you can modify the adapter information with `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
     <span data-ttu-id="35f17-111">2 つの方法は似ていますが、`SetAdapterProperties`構成情報が変更されたときに、アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="35f17-111">While the two methods are similar, `SetAdapterProperties` sends a message to the adapter when the configuration information changes.</span></span>  
  
3.  <span data-ttu-id="35f17-112">アダプターを削除するには、ISSOAdmin.DeleteApplication を使用します。</span><span class="sxs-lookup"><span data-stu-id="35f17-112">To delete an adapter, use ISSOAdmin.DeleteApplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f17-113">参照</span><span class="sxs-lookup"><span data-stu-id="35f17-113">See Also</span></span>  
 [<span data-ttu-id="35f17-114">パスワードの同期</span><span class="sxs-lookup"><span data-stu-id="35f17-114">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)