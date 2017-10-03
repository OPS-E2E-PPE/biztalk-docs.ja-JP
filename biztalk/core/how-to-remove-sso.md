---
title: "SSO を削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, deleting
- SSO, deleting
- deleting, SSO
- deleting, Master Secret server
ms.assetid: 0e1ad8e3-0938-4f36-b85b-4631d0eeb8c9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7134186161c3c0647a20047afcbbe317fcbad1ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-sso"></a><span data-ttu-id="7df65-102">SSO を削除する方法</span><span class="sxs-lookup"><span data-stu-id="7df65-102">How to Remove SSO</span></span>
<span data-ttu-id="7df65-103">BizTalk Server を削除すると、エンタープライズ シングル サインオン (SSO) を必要とする製品で SSO が使用されていない限り、SSO の構成は解除されます。</span><span class="sxs-lookup"><span data-stu-id="7df65-103">If you remove BizTalk Server, Enterprise Single Sign-On (SSO) is no longer configured unless a dependent product is using it.</span></span> <span data-ttu-id="7df65-104">ただし、SSO は削除されません。</span><span class="sxs-lookup"><span data-stu-id="7df65-104">However, it is not removed.</span></span> <span data-ttu-id="7df65-105">SSO は個別に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7df65-105">You must remove SSO separately.</span></span> <span data-ttu-id="7df65-106">また、マスタ シークレットなどの構成情報を復元して、既存のデータを再利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7df65-106">You can also restore configuration information including the master secret to reuse existing data.</span></span> <span data-ttu-id="7df65-107">詳細については、次を参照してください。[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="7df65-107">For more information, see [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="to-remove-enterprise-single-sign-on"></a><span data-ttu-id="7df65-108">エンタープライズ シングル サインオンを削除するには</span><span class="sxs-lookup"><span data-stu-id="7df65-108">To remove Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="7df65-109">マスタ シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="7df65-109">Back up the master secret key.</span></span> <span data-ttu-id="7df65-110">詳細については、次を参照してください。[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="7df65-110">For more information, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2.  <span data-ttu-id="7df65-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="7df65-111">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="7df65-112">**[スタート]** ボタンをクリックし、 **[コントロール パネル]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7df65-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
4.  <span data-ttu-id="7df65-113">をクリックして**プログラムの追加/削除**です。</span><span class="sxs-lookup"><span data-stu-id="7df65-113">Click **Add/Remove Programs**.</span></span>  
  
5.  <span data-ttu-id="7df65-114">**プログラムの追加/削除**ダイアログ ボックスで、をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**削除**です。</span><span class="sxs-lookup"><span data-stu-id="7df65-114">In the **Add/Remove Programs** dialog box, click **Microsoft Enterprise Single Sign-On**, and then click **Remove**.</span></span>  
  
6.  <span data-ttu-id="7df65-115">をクリックして**はい**Microsoft エンタープライズ シングル サインオンの削除の確認を求められたらです。</span><span class="sxs-lookup"><span data-stu-id="7df65-115">Click **Yes** when prompted to confirm the removal of Microsoft Enterprise Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7df65-116">BizTalk Server のランタイム機能、開発機能、または管理機能がインストールされているか、または Host Integration Server の管理機能がインストールされている場合、すべての依存関係を削除するまで SSO ランタイム コンポーネントや管理コンポーネントはアンインストールできません。</span><span class="sxs-lookup"><span data-stu-id="7df65-116">If you have BizTalk Server Runtime, Development, or Administration features installed, or Host Integration Server Administration features installed, you will not be able to uninstall the SSO Runtime or Administration components until all dependencies are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df65-117">参照</span><span class="sxs-lookup"><span data-stu-id="7df65-117">See Also</span></span>  
 [<span data-ttu-id="7df65-118">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="7df65-118">Installing SSO</span></span>](../core/installing-sso.md)