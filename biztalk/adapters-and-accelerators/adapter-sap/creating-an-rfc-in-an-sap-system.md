---
title: "SAP アダプターの BizTalk で使用する SAP RFC の作成の概要 |Microsoft ドキュメント"
description: "作成、RFC では、RFC 変換先、および送信 SAP システム - BizTalk アダプター パック (BAP) の RFC"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802a2e33b8bc902dc784276ce7c1d9c3f37f3b12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-and-send-an-rfc-in-sap"></a><span data-ttu-id="8bd14-103">作成および送信 RFC SAP</span><span class="sxs-lookup"><span data-stu-id="8bd14-103">Create and send an RFC in SAP</span></span>
<span data-ttu-id="8bd14-104">RFC を作成する SAP システムで完了する高度なタスクを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-104">Lists high-level tasks to complete on the SAP system to create an RFC.</span></span> <span data-ttu-id="8bd14-105">各タスクには、非常に詳細な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8bd14-105">Each task may involve very detailed procedures.</span></span> <span data-ttu-id="8bd14-106">その結果、これらのタスクを完了または SAP ガイダンスを参照してください、SAP 管理者に連絡をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bd14-106">As a result, we recommend contacting your SAP administrator to complete these tasks, or refer to the SAP guidance.</span></span>  
  
## <a name="create-an-rfc"></a><span data-ttu-id="8bd14-107">RFC を作成します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-107">Create an RFC</span></span>  
  
1.  <span data-ttu-id="8bd14-108">SAP の GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-108">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="8bd14-109">トランザクション SE37 に移動 (関数ビルダー) は、RFC 名を入力し、をクリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="8bd14-109">Go to Transaction SE37 (Function Builder), enter the RFC name, and click **Create**.</span></span>  
  
3.  <span data-ttu-id="8bd14-110">既存関数のグループでは、RFC が作成されるの RFC の簡単な説明を入力し、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="8bd14-110">Enter an existing function group under which the RFC will be created, a short description for the RFC, and click **Save**.</span></span>  
  
4.  <span data-ttu-id="8bd14-111">**属性**] タブで、[、 **Remote-Enabled モジュール**ラジオ ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bd14-111">In the **Attributes** tab, select the **Remote-Enabled Module** radio button.</span></span>  
  
5.  <span data-ttu-id="8bd14-112">**インポート** タブで、インポートのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-112">In the **Import** tab, enter the import parameters.</span></span> <span data-ttu-id="8bd14-113">これらのパラメーターは、関数モジュールに、外部データを渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bd14-113">These parameters are used for passing the external data to the function module.</span></span>  
  
6.  <span data-ttu-id="8bd14-114">**エクスポート** タブで、エクスポートのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-114">In the **Export** tab, enter the export parameters.</span></span>  
  
7.  <span data-ttu-id="8bd14-115">**Changing**  タブを変化させるパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-115">In the **Changing** tab, enter the changing parameters.</span></span>  
  
8.  <span data-ttu-id="8bd14-116">**テーブル** タブで、テーブル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-116">In the **Tables** tab, enter the table names.</span></span>  
  
9. <span data-ttu-id="8bd14-117">**例外** タブで、エラーを処理する例外を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-117">In the **Exceptions** tab, enter the exceptions to handle errors.</span></span>  
  
10. <span data-ttu-id="8bd14-118">**ソース コード** タブで、RFC のソース コード (ロジック) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-118">In the **Source Code** tab, enter the source code (logic) for the RFC.</span></span>  
  
11. <span data-ttu-id="8bd14-119">クリックして、 **Activate**関数モジュールをアクティブ化するツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="8bd14-119">Click the **Activate** icon on the toolbar to activate the function module.</span></span>  

## <a name="create-an-rfc-destination"></a><span data-ttu-id="8bd14-120">RFC 変換先を作成します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-120">Create an RFC destination</span></span>  
  
1.  <span data-ttu-id="8bd14-121">SAP の GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-121">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="8bd14-122">トランザクション SM59 に移動 (表示および RFC 転送先の管理)。</span><span class="sxs-lookup"><span data-stu-id="8bd14-122">Go to Transaction SM59 (Display and Maintain RFC Destinations).</span></span>  
  
3.  <span data-ttu-id="8bd14-123">メニュー バーからをクリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="8bd14-123">From the menu bar, click **Create**.</span></span>  
  
4.  <span data-ttu-id="8bd14-124">RFC 転送先の接続の種類、説明を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-124">Enter the RFC destination, connection type, description, and then press Enter.</span></span>  
  
5.  <span data-ttu-id="8bd14-125">選択、**登録済みサーバーのプログラム**ラジオ ボタン、プログラム ID、ゲートウェイのホスト、およびゲートウェイ サービスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-125">Select the **Registered Server Program** radio-button, enter the program ID, gateway host, and gateway service.</span></span>  
  
6.  <span data-ttu-id="8bd14-126">RFC 転送先を保存します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-126">Save the RFC destination.</span></span>  

## <a name="send-an-rfc-from-an-sap-system"></a><span data-ttu-id="8bd14-127">SAP システムからの RFC を送信します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-127">Send an RFC from an SAP system</span></span>  
  
1.  <span data-ttu-id="8bd14-128">SAP の GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-128">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="8bd14-129">BD54 トランザクションを使用して論理システムを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-129">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="8bd14-130">SM59 トランザクションを使用して TCP/IP 接続で、RFC 変換先を作成します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-130">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="8bd14-131">WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。</span><span class="sxs-lookup"><span data-stu-id="8bd14-131">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="8bd14-132">SE37 を使用して、RFC をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="8bd14-132">Trigger an RFC by using SE37.</span></span> <span data-ttu-id="8bd14-133">この RFC では、外部アプリケーションへの呼び出しし、そのアプリケーションからの応答を受信し、RFC を作成するためのロジックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bd14-133">This RFC must contain the logic to make an RFC call to an external application and then receive a response from that application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd14-134">参照</span><span class="sxs-lookup"><span data-stu-id="8bd14-134">See Also</span></span>  
 [<span data-ttu-id="8bd14-135">特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8bd14-135">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)