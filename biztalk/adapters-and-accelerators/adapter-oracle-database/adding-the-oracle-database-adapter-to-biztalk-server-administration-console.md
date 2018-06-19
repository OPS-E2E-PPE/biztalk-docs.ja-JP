---
title: BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d71e161-addc-47d4-9103-3655f3fb0b0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f004fe7e7355812923f2d218380e4e4ff1f04c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214994"
---
# <a name="adding-the-oracle-database-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="f395d-102">BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加</span><span class="sxs-lookup"><span data-stu-id="f395d-102">Adding the Oracle Database Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="f395d-103">このトピックへの Wcf-oracledb アダプターを追加する方法の説明、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f395d-103">This topic provides instructions on how to add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f395d-104">実行する必要はありませんこれらのタスクの WCF カスタム ポートを構成する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f395d-104">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="add-the-oracle-database-adapter"></a><span data-ttu-id="f395d-105">Oracle データベース アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="f395d-105">Add the Oracle Database Adapter</span></span>  
  
1.  <span data-ttu-id="f395d-106">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f395d-106">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f395d-107">展開して、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="f395d-107">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3.  <span data-ttu-id="f395d-108">右クリック**アダプター****新規**を選択して**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="f395d-108">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
     <span data-ttu-id="f395d-109">![アダプタの追加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="f395d-109">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="f395d-110">**アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を入力、**アダプター**一覧で、[ **Wcf-oracledb**です。</span><span class="sxs-lookup"><span data-stu-id="f395d-110">In the **Adapter Properties** dialog box, enter a name for the adapter and from the **Adapter** list, select **WCF-OracleDB**.</span></span>  
  
     <span data-ttu-id="f395d-111">![追加の WCF &#45; OracleDB アダプターを BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span><span class="sxs-lookup"><span data-stu-id="f395d-111">![Adding WCF&#45;OracleDB adapter to BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span></span>  
  
5.  <span data-ttu-id="f395d-112">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f395d-112">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f395d-113">参照</span><span class="sxs-lookup"><span data-stu-id="f395d-113">See Also</span></span>  
[<span data-ttu-id="f395d-114">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="f395d-114">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)