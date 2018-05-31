---
title: シングル サインオンの要件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2a1fb342911c904044c8099901c5056f17ac9f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013025"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="cebaf-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="cebaf-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="cebaf-103">シングル サインオン (SSO) を使用するのには、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="cebaf-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
-   <span data-ttu-id="cebaf-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cebaf-104">Microsoft BizTalk Server</span></span> 
  
-   <span data-ttu-id="cebaf-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cebaf-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="cebaf-106">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cebaf-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="cebaf-107">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="cebaf-107">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="cebaf-108">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebaf-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="cebaf-109">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cebaf-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="cebaf-110">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="cebaf-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="cebaf-111">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cebaf-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="cebaf-112">関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。</span><span class="sxs-lookup"><span data-stu-id="cebaf-112">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cebaf-113">作業を実行した後、SSO の使用に注意してくださいをリセットする**Web 共有**フォルダー**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="cebaf-113">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="cebaf-114">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="cebaf-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cebaf-115">参照</span><span class="sxs-lookup"><span data-stu-id="cebaf-115">See Also</span></span>  
 [<span data-ttu-id="cebaf-116">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="cebaf-116">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)