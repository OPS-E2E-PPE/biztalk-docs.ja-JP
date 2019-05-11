---
title: SAP アダプターの BizTalk で使用する SAP の RFC の作成の概要 |Microsoft Docs
description: 作成、RFC と RFC 変換先、および BizTalk アダプター パック (BAP) の SAP システムから RFC を送信
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c05fb0b0c987c4f04115f6872056beeaf260355
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373538"
---
# <a name="create-and-send-an-rfc-in-sap"></a><span data-ttu-id="d4cc0-103">作成し、SAP で RFC を送信</span><span class="sxs-lookup"><span data-stu-id="d4cc0-103">Create and send an RFC in SAP</span></span>
<span data-ttu-id="d4cc0-104">RFC を作成する SAP システムで完了する高度なタスクを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-104">Lists high-level tasks to complete on the SAP system to create an RFC.</span></span> <span data-ttu-id="d4cc0-105">各タスクには、非常に詳細な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-105">Each task may involve very detailed procedures.</span></span> <span data-ttu-id="d4cc0-106">その結果、これらのタスクを完了または SAP のガイダンスをご覧ください SAP 管理者に連絡をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-106">As a result, we recommend contacting your SAP administrator to complete these tasks, or refer to the SAP guidance.</span></span>  
  
## <a name="create-an-rfc"></a><span data-ttu-id="d4cc0-107">RFC を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-107">Create an RFC</span></span>  
  
1.  <span data-ttu-id="d4cc0-108">SAP GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-108">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="d4cc0-109">トランザクション SE37 に移動 (関数ビルダー) は、RFC 名を入力し、をクリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-109">Go to Transaction SE37 (Function Builder), enter the RFC name, and click **Create**.</span></span>  
  
3.  <span data-ttu-id="d4cc0-110">既存関数のグループでは、RFC が作成される、RFC の短い説明を入力し、クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-110">Enter an existing function group under which the RFC will be created, a short description for the RFC, and click **Save**.</span></span>  
  
4.  <span data-ttu-id="d4cc0-111">**属性**] タブで、[、 **Remote-Enabled モジュール**ラジオ ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-111">In the **Attributes** tab, select the **Remote-Enabled Module** radio button.</span></span>  
  
5.  <span data-ttu-id="d4cc0-112">**インポート** タブで、インポートのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-112">In the **Import** tab, enter the import parameters.</span></span> <span data-ttu-id="d4cc0-113">これらのパラメーターは、関数モジュールを外部のデータを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-113">These parameters are used for passing the external data to the function module.</span></span>  
  
6.  <span data-ttu-id="d4cc0-114">**エクスポート** タブで、エクスポートのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-114">In the **Export** tab, enter the export parameters.</span></span>  
  
7.  <span data-ttu-id="d4cc0-115">**Changing**  タブで、変化するパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-115">In the **Changing** tab, enter the changing parameters.</span></span>  
  
8.  <span data-ttu-id="d4cc0-116">**テーブル**タブで、テーブル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-116">In the **Tables** tab, enter the table names.</span></span>  
  
9. <span data-ttu-id="d4cc0-117">**例外** タブで、エラーを処理する例外を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-117">In the **Exceptions** tab, enter the exceptions to handle errors.</span></span>  
  
10. <span data-ttu-id="d4cc0-118">**ソース コード**タブで、RFC のソース コード (ロジック) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-118">In the **Source Code** tab, enter the source code (logic) for the RFC.</span></span>  
  
11. <span data-ttu-id="d4cc0-119">をクリックして、 **Activate**関数モジュールをアクティブ化するには、ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-119">Click the **Activate** icon on the toolbar to activate the function module.</span></span>  

## <a name="create-an-rfc-destination"></a><span data-ttu-id="d4cc0-120">RFC 転送先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-120">Create an RFC destination</span></span>  
  
1.  <span data-ttu-id="d4cc0-121">SAP GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-121">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="d4cc0-122">トランザクション SM59 に移動 (表示し、RFC 転送先の管理)。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-122">Go to Transaction SM59 (Display and Maintain RFC Destinations).</span></span>  
  
3.  <span data-ttu-id="d4cc0-123">メニュー バーで、次のようにクリックします。**作成**です。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-123">From the menu bar, click **Create**.</span></span>  
  
4.  <span data-ttu-id="d4cc0-124">RFC 転送先の接続の種類、説明を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-124">Enter the RFC destination, connection type, description, and then press Enter.</span></span>  
  
5.  <span data-ttu-id="d4cc0-125">選択、**登録済みサーバーのプログラム**オプション ボタンのプログラム ID、ゲートウェイ ホスト、およびゲートウェイ サービスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-125">Select the **Registered Server Program** radio-button, enter the program ID, gateway host, and gateway service.</span></span>  
  
6.  <span data-ttu-id="d4cc0-126">RFC 転送先を保存します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-126">Save the RFC destination.</span></span>  

## <a name="send-an-rfc-from-an-sap-system"></a><span data-ttu-id="d4cc0-127">SAP システムから RFC を送信します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-127">Send an RFC from an SAP system</span></span>  
  
1.  <span data-ttu-id="d4cc0-128">SAP GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-128">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="d4cc0-129">BD54 トランザクションを使用して論理システムを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-129">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="d4cc0-130">SM59 トランザクションを使用して TCP/IP 接続では、RFC 転送先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-130">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="d4cc0-131">WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-131">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="d4cc0-132">SE37 を使用して、RFC をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-132">Trigger an RFC by using SE37.</span></span> <span data-ttu-id="d4cc0-133">この RFC では、RFC 外部アプリケーションへの呼び出しし、そのアプリケーションからの応答を受信するロジックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-133">This RFC must contain the logic to make an RFC call to an external application and then receive a response from that application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cc0-134">参照</span><span class="sxs-lookup"><span data-stu-id="d4cc0-134">See Also</span></span>  
 [<span data-ttu-id="d4cc0-135">特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4cc0-135">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)