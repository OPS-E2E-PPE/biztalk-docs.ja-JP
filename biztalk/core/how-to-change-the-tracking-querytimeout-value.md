---
title: 追跡 QueryTimeout 値を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca9f61466323e0b154bdeb0499cc5cee6e4ef10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247474"
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a><span data-ttu-id="66f7f-102">追跡 QueryTimeout 値の変更方法</span><span class="sxs-lookup"><span data-stu-id="66f7f-102">How to Change the Tracking QueryTimeout Value</span></span>
<span data-ttu-id="66f7f-103">既定では、クエリの実行時間が 60 秒を超えると、メッセージとサービス インスタンスの追跡はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="66f7f-103">By default, message and service instance tracking will time out if a query runs longer than 60 seconds.</span></span> <span data-ttu-id="66f7f-104">レジストリでタイムアウトの値を変更することで、60 秒より長くクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="66f7f-104">You can change the timeout value in the registry to enable queries to run longer than 60 seconds.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="66f7f-105">レジストリの編集を誤ると、システムに深刻な悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66f7f-105">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="66f7f-106">レジストリを変更する前に、コンピューター上のすべての重要なデータをバックアップしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66f7f-106">Before making changes to the registry, you should back up any valued data on the computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66f7f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="66f7f-107">Prerequisites</span></span>  
 <span data-ttu-id="66f7f-108">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f7f-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-change-the-query-timeout-value"></a><span data-ttu-id="66f7f-109">クエリのタイムアウト値を変更するには</span><span class="sxs-lookup"><span data-stu-id="66f7f-109">To change the query timeout value</span></span>  
  
1.  <span data-ttu-id="66f7f-110">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="66f7f-110">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="66f7f-111">レジストリ エディターで、次のサブキーを探してクリックします。</span><span class="sxs-lookup"><span data-stu-id="66f7f-111">In Registry Editor, locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="66f7f-112">**Hkey_local_machine \software\microsoft\biztalk server \3.0**</span><span class="sxs-lookup"><span data-stu-id="66f7f-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**</span></span>  
  
3.  <span data-ttu-id="66f7f-113">Tracking サブキーがある場合は、手順 6. へ進みます。</span><span class="sxs-lookup"><span data-stu-id="66f7f-113">If there is a Tracking subkey, go to step 6.</span></span>  
  
4.  <span data-ttu-id="66f7f-114">Tracking サブキーを作成する、**編集** メニューのをポイント**新規**、順にクリック**キー**です。</span><span class="sxs-lookup"><span data-stu-id="66f7f-114">To create a Tracking subkey, on the **Edit** menu, point to **New**, and then click **Key**.</span></span>  
  
5.  <span data-ttu-id="66f7f-115">型**追跡**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="66f7f-115">Type **Tracking**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="66f7f-116">次のサブキーを探してクリックします。</span><span class="sxs-lookup"><span data-stu-id="66f7f-116">Locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="66f7f-117">**Hkey_local_machine Server\3.0\Tracking**</span><span class="sxs-lookup"><span data-stu-id="66f7f-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span></span>  
  
7.  <span data-ttu-id="66f7f-118">**編集** メニューのをポイント**新規**、クリックして**DWORD 値**です。</span><span class="sxs-lookup"><span data-stu-id="66f7f-118">On the **Edit** menu, point to **New**, and then click **DWORD Value**.</span></span>  
  
8.  <span data-ttu-id="66f7f-119">型**ConnectionTimeout**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="66f7f-119">Type **ConnectionTimeout**, and then press ENTER.</span></span>  
  
9. <span data-ttu-id="66f7f-120">右クリック**ConnectionTimeout**、クリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="66f7f-120">Right-click **ConnectionTimeout**, and then click **Modify**.</span></span>  
  
10. <span data-ttu-id="66f7f-121">**DWORD 値の編集**ダイアログ ボックスで、をクリックして**Decimal**です。</span><span class="sxs-lookup"><span data-stu-id="66f7f-121">In the **Edit DWORD Value** dialog box, click **Decimal**.</span></span>  
  
11. <span data-ttu-id="66f7f-122">**値のデータ**ボックスには、クエリのタイムアウト値を設定し、をクリックする秒単位で値を入力**OK**です。</span><span class="sxs-lookup"><span data-stu-id="66f7f-122">In the **Value data** box, type the value in seconds that you want to set for the query timeout value, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="66f7f-123">**[ファイル]** メニューの **[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66f7f-123">On the **File** menu, click **Exit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66f7f-124">新しいタイムアウト値を有効にするには、BizTalk Server 管理コンソールを閉じて再び開くことが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="66f7f-124">You may need to close and then reopen the BizTalk Server Administration Console in order for the new timeout value to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f7f-125">参照</span><span class="sxs-lookup"><span data-stu-id="66f7f-125">See Also</span></span>  
 [<span data-ttu-id="66f7f-126">履歴および追跡データを表示します。</span><span class="sxs-lookup"><span data-stu-id="66f7f-126">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)