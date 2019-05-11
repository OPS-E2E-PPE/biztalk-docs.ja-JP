---
title: BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加 |Microsoft Docs
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
ms.openlocfilehash: f2a08982e8e58e9333c52121b9be9da4aecd7f37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376826"
---
# <a name="adding-the-oracle-database-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="10571-102">BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加</span><span class="sxs-lookup"><span data-stu-id="10571-102">Adding the Oracle Database Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="10571-103">このトピックでは、Wcf-oracledb アダプターを追加する方法を手順については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="10571-103">This topic provides instructions on how to add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10571-104">WCF カスタム ポートを構成する場合これらのタスクを実行する必要ありません、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="10571-104">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="add-the-oracle-database-adapter"></a><span data-ttu-id="10571-105">Oracle データベース アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="10571-105">Add the Oracle Database Adapter</span></span>  
  
1. <span data-ttu-id="10571-106">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="10571-106">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="10571-107">展開、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="10571-107">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3. <span data-ttu-id="10571-108">右クリック**アダプター**を選択します**新規**、選び**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="10571-108">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
    <span data-ttu-id="10571-109">![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="10571-109">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="10571-110">**アダプター プロパティ**] ダイアログ ボックスに、アダプターとの間の名前を入力、**アダプター**一覧で、[ **Wcf-oracledb**します。</span><span class="sxs-lookup"><span data-stu-id="10571-110">In the **Adapter Properties** dialog box, enter a name for the adapter and from the **Adapter** list, select **WCF-OracleDB**.</span></span>  
  
    <span data-ttu-id="10571-111">![WCF の追加&#45;OracleDB アダプターを BizTalk Server に](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span><span class="sxs-lookup"><span data-stu-id="10571-111">![Adding WCF&#45;OracleDB adapter to BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span></span>  
  
5. <span data-ttu-id="10571-112">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="10571-112">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10571-113">参照</span><span class="sxs-lookup"><span data-stu-id="10571-113">See Also</span></span>  
[<span data-ttu-id="10571-114">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="10571-114">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)