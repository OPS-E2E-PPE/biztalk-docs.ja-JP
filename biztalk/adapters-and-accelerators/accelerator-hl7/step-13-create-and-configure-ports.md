---
title: "手順 13: が作成し、ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c1b18e5b7addf1bae390dd541b84d17bd94023d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-13-create-and-configure-ports"></a><span data-ttu-id="186a9-102">手順 13: を作成し、ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="186a9-102">Step 13: Create and Configure Ports</span></span>
<span data-ttu-id="186a9-103">このステップでは、ポート構成ウィザードを使用して作成し、オーケストレーション デザイナーでポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="186a9-103">In this step, you use the Port Configuration Wizard to create and configure ports in Orchestration Designer.</span></span> <span data-ttu-id="186a9-104">オーケストレーションの送信し、ビジネス プロセスからメッセージを送受信ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="186a9-104">Ports specify how your orchestration sends and receives messages to and from business processes.</span></span> <span data-ttu-id="186a9-105">各ポートには、種類、方向、およびバインドします。</span><span class="sxs-lookup"><span data-stu-id="186a9-105">Each port has a type, a direction, and a binding.</span></span> <span data-ttu-id="186a9-106">プロパティは、通信、通信のパターン、元の場所の方向を一緒に決定[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を送信または受信メッセージとの通信が行われる方法です。</span><span class="sxs-lookup"><span data-stu-id="186a9-106">The properties together determine the direction of communication, the pattern of communication, the location to or from which [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] sends or receives the message, and how the communication takes place.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="186a9-107">送信ポートとして最小下位層プロトコル (MLLP) アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="186a9-107"> uses the Minimum Lower Layer Protocol (MLLP) adapter as a send port.</span></span> <span data-ttu-id="186a9-108">MLLP アダプターは、他のラボ アプリケーションなどのアプリケーション、保険アプリケーションは、従来の基幹業務アプリケーションとのインターフェイスに TCP ソケット通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="186a9-108">The MLLP adapter uses TCP sockets communication to interface with other applications, such as laboratory applications, insurance applications, and legacy line-of-business applications.</span></span> <span data-ttu-id="186a9-109">MLLP 送信アダプターを表す、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]はアダプター。</span><span class="sxs-lookup"><span data-stu-id="186a9-109">The MLLP Send Adapter represents a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adapter that is:</span></span>  
  
-   <span data-ttu-id="186a9-110">カスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="186a9-110">Customized.</span></span> <span data-ttu-id="186a9-111">アダプターにのみ付属して[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]に付属して BizTalk Server ではなく、します。</span><span class="sxs-lookup"><span data-stu-id="186a9-111">The adapter only ships with [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], as opposed to shipping with BizTalk Server.</span></span>  
  
-   <span data-ttu-id="186a9-112">プロトコル/トランスポート。</span><span class="sxs-lookup"><span data-stu-id="186a9-112">Protocol/Transport.</span></span> <span data-ttu-id="186a9-113">アダプターは、アプリケーションまたはデータ アダプターではありません。</span><span class="sxs-lookup"><span data-stu-id="186a9-113">The adapter is not an application or data adapter.</span></span>  
  
-   <span data-ttu-id="186a9-114">静的です。</span><span class="sxs-lookup"><span data-stu-id="186a9-114">Static.</span></span> <span data-ttu-id="186a9-115">アダプターの構成では、カスタム ユーザー インターフェイスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="186a9-115">The adapter configuration does not involve a custom user interface.</span></span>  
  
-   <span data-ttu-id="186a9-116">非同期です。</span><span class="sxs-lookup"><span data-stu-id="186a9-116">Asynchronous.</span></span> <span data-ttu-id="186a9-117">アダプターがすべてのアダプターのパフォーマンスを向上できるメッセージング エンジン スレッドをブロックしていないを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホストします。</span><span class="sxs-lookup"><span data-stu-id="186a9-117">The adapter does not block the Messaging Engine thread, which enables increased performance of all adapters that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hosts.</span></span>  
  
-   <span data-ttu-id="186a9-118">非トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="186a9-118">Nontransacted.</span></span> <span data-ttu-id="186a9-119">アダプターはトランザクション処理された受信または送信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="186a9-119">The adapter is not a transacted receive or send [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adapter.</span></span>  
  
-   <span data-ttu-id="186a9-120">正規です。</span><span class="sxs-lookup"><span data-stu-id="186a9-120">Regular.</span></span> <span data-ttu-id="186a9-121">アダプターは、別のアプリケーション プロセスでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="186a9-121">The adapter does not run in a separate application process.</span></span>  
  
-   <span data-ttu-id="186a9-122">一方向と双方向です。</span><span class="sxs-lookup"><span data-stu-id="186a9-122">Both One-Way and Two-Way.</span></span> <span data-ttu-id="186a9-123">アダプターは、相互作用の一方向および要求-応答/送信請求-応答の両方のモードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="186a9-123">The adapter supports both One-way and Request-Response/Solicit-Response modes of interaction.</span></span>  
  
 <span data-ttu-id="186a9-124">MLLP アダプターでは、個々 のメッセージを送信したり、バッチ内のメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="186a9-124">The MLLP adapter can submit individual messages or submit messages in a batch.</span></span> <span data-ttu-id="186a9-125">MLLP メッセージの先頭がラッパー文字、16 進 0x0b (とも呼ばれる、ブロックの開始] または [SB 文字) でマークされているし、16 進数の 0x1c 文字 (End ブロックまたは EB 文字とも呼ばれます) の組み合わせによって、メッセージの最後をマークすぐに続く、0x0d 文字 (キャリッジ リターン)。</span><span class="sxs-lookup"><span data-stu-id="186a9-125">The beginning of an MLLP message is marked with a wrapper character, hexadecimal 0x0b (also known as the Start Block or SB character), and the end of the message is marked by the combination of a hexadecimal 0x1c character (also known as the End Block or EB character) immediately followed by the 0x0d character (Carriage Return).</span></span> <span data-ttu-id="186a9-126">BTAHL7 パフォーマンス カウンターは、送信メッセージに対してこれらのラッパー文字のみをカウントします。</span><span class="sxs-lookup"><span data-stu-id="186a9-126">BTAHL7 performance counters only count these wrapper characters for sent messages.</span></span> <span data-ttu-id="186a9-127">BTAHL7 パフォーマンス カウンターでは、メッセージを受信するときにこれらのラッパーの文字はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="186a9-127">BTAHL7 performance counters do not count these wrapper characters when receiving messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="186a9-128">SB と EB 文字を検出する機能に支障があるために、標準 MLLP のプロトコルは、メッセージ ペイロードの 0x20 下にある文字を許可されません。</span><span class="sxs-lookup"><span data-stu-id="186a9-128">The MLLP protocol standard does not allow characters under 0x20 in the message payload because it interferes with the ability to detect the SB and EB characters.</span></span> <span data-ttu-id="186a9-129">SB と EB の文字の値を構成、のでくれぐれもこの問題が発生した変更を行うときにできます。</span><span class="sxs-lookup"><span data-stu-id="186a9-129">You can configure the SB and EB character values, so be wary of this issue when making changes.</span></span>  
  
 <span data-ttu-id="186a9-130">この手順では、MLLP アダプターおよび SOAP アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="186a9-130">In this step, you configure the MLLP adapter and SOAP adapter.</span></span>  
  
### <a name="to-create-and-configure-the-ports"></a><span data-ttu-id="186a9-131">ポートを作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="186a9-131">To create and configure the ports</span></span>  
  
1.  <span data-ttu-id="186a9-132">オーケストレーション デザイナーで、ドラッグ、**ポート**ツールボックスから図形をデザイン ビューの左側にあるポート画面およびで水平方向に合わせて配置されるようにドロップします、 **DoorbellReceive**図形です。</span><span class="sxs-lookup"><span data-stu-id="186a9-132">In Orchestration Designer, drag the **Port** shape from the Toolbox to the Port Surface on the left side of the Design view surface, and drop the shape so that it aligns horizontally with the **DoorbellReceive** shape.</span></span>  
  
2.  <span data-ttu-id="186a9-133">**ポート構成ウィザード**をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-133">In the **Port Configuration Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="186a9-134">**ポートのプロパティ**] ページの [、**名前**フィールドに「 **SOAPReceivePort**、クリックしてして**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-134">On the **Port Properties** page, in the **Name** field, type **SOAPReceivePort**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="186a9-135">**ポートの種類を選択して** ページで、次の情報を入力してをクリックして**次へ**を続行します。</span><span class="sxs-lookup"><span data-stu-id="186a9-135">On the **Select a Port Type** page, enter the following information, and then click **Next** to continue.</span></span>  
  
    |<span data-ttu-id="186a9-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="186a9-136">Use this</span></span>|<span data-ttu-id="186a9-137">目的</span><span class="sxs-lookup"><span data-stu-id="186a9-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="186a9-138">**ポートの種類名**</span><span class="sxs-lookup"><span data-stu-id="186a9-138">**Port Type Name**</span></span>|<span data-ttu-id="186a9-139">型**SOAPReceivePortType**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-139">Type **SOAPReceivePortType**.</span></span>|  
    |<span data-ttu-id="186a9-140">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="186a9-140">**Communication Pattern**</span></span>|<span data-ttu-id="186a9-141">選択**一方向**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-141">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="186a9-142">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="186a9-142">**Access Restrictions**</span></span>|<span data-ttu-id="186a9-143">選択**パブリック - 制限なし**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-143">Select **Public - no limit**.</span></span>|  
  
5.  <span data-ttu-id="186a9-144">**ポートのバインド** ページで、をクリックして**次**既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="186a9-144">On the **Port Binding** page, click **Next** to accept the default values.</span></span>  
  
6.  <span data-ttu-id="186a9-145">**ポート ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
7.  <span data-ttu-id="186a9-146">ドラッグ、**ポート**ツールボックスから図形をデザイン ビューの右側にあるポート画面およびで水平方向に合わせて配置されるようにドロップします、 **DoorbellSend**図形です。</span><span class="sxs-lookup"><span data-stu-id="186a9-146">Drag the **Port** shape from the Toolbox to the Port Surface on the right side of the Design view surface, and drop the shape so that it aligns horizontally with the **DoorbellSend** shape.</span></span>  
  
8.  <span data-ttu-id="186a9-147">使用して、**ポート構成ウィザード**場合と同様の手順 2. ~ 7. で、次のパラメーターを使用して追加の送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="186a9-147">Using the **Port Configuration Wizard** as you did in steps 2 through 7, create an additional send port using the following parameters:</span></span>  
  
    |<span data-ttu-id="186a9-148">プロパティ</span><span class="sxs-lookup"><span data-stu-id="186a9-148">Property</span></span>|<span data-ttu-id="186a9-149">パラメーター</span><span class="sxs-lookup"><span data-stu-id="186a9-149">Parameter</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="186a9-150">**ポートのプロパティ名**</span><span class="sxs-lookup"><span data-stu-id="186a9-150">**Port Properties Name**</span></span>|<span data-ttu-id="186a9-151">MLLPSendPort</span><span class="sxs-lookup"><span data-stu-id="186a9-151">MLLPSendPort</span></span>|  
    |<span data-ttu-id="186a9-152">**ポートの種類名**</span><span class="sxs-lookup"><span data-stu-id="186a9-152">**Port Type Name**</span></span>|<span data-ttu-id="186a9-153">MLLPSendPortType</span><span class="sxs-lookup"><span data-stu-id="186a9-153">MLLPSendPortType</span></span>|  
    |<span data-ttu-id="186a9-154">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="186a9-154">**Communication Pattern**</span></span>|<span data-ttu-id="186a9-155">一方向</span><span class="sxs-lookup"><span data-stu-id="186a9-155">One-Way</span></span>|  
    |<span data-ttu-id="186a9-156">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="186a9-156">**Access Restrictions**</span></span>|<span data-ttu-id="186a9-157">パブリック - 制限なし</span><span class="sxs-lookup"><span data-stu-id="186a9-157">Public - no limit</span></span>|  
    |<span data-ttu-id="186a9-158">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="186a9-158">**Port Binding**</span></span>|<span data-ttu-id="186a9-159">[後で指定する]</span><span class="sxs-lookup"><span data-stu-id="186a9-159">Specify Later</span></span>|  
    |<span data-ttu-id="186a9-160">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="186a9-160">**Port direction of communication**</span></span>|<span data-ttu-id="186a9-161">常にこのポートでメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="186a9-161">I'll always be sending messages on this port.</span></span>|  
  
9. <span data-ttu-id="186a9-162">**オーケストレーションの種類** ウィンドウで、**型**、**ポートの種類**、および**SOAPReceivePortType** を展開するノードを展開すると、**Operation_1**、クリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-162">In the **Orchestration View** window, with the **Types**, **Ports Types**, and **SOAPReceivePortType** nodes expanded, expand **Operation_1**, and then click **Request**.</span></span>  
  
10. <span data-ttu-id="186a9-163">**プロパティ** ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、クリックして**BTAHL7_Project.Doorbell**.</span><span class="sxs-lookup"><span data-stu-id="186a9-163">In the **Properties** window, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7_Project.Doorbell**.</span></span>  
  
11. <span data-ttu-id="186a9-164">**オーケストレーションの種類**ウィンドウで、展開**MLLPSendPortType**、展開**Operation_1**、順にクリック**要求**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-164">In the **Orchestration View** window, expand **MLLPSendPortType**, expand **Operation_1**, and then click **Request**.</span></span>  
  
12. <span data-ttu-id="186a9-165">**プロパティ** ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**マルチパート メッセージの種類**、クリックして**BTAHL7_Project.DoorbellFinalMessageType**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-165">In the **Properties** window, in the drop-down list for **Message Type**, expand **Multi-part Message Types**, and then click **BTAHL7_Project.DoorbellFinalMessageType**.</span></span>  
  
13. <span data-ttu-id="186a9-166">**名前**フィールドに「**応答**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-166">In the **Name** field, type **Response**, then press **Enter**.</span></span>  
  
14. <span data-ttu-id="186a9-167">オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellReceive**アクション図形。</span><span class="sxs-lookup"><span data-stu-id="186a9-167">On the orchestration Design view surface, click the **DoorbellReceive** action shape.</span></span>  
  
15. <span data-ttu-id="186a9-168">**プロパティ**] ウィンドウのドロップダウン リストで、**メッセージ**[ **DoorbellInputMessage**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-168">In the **Properties** window, in the drop-down list for **Message**, select **DoorbellInputMessage**.</span></span>  
  
16. <span data-ttu-id="186a9-169">オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellSend**図形です。</span><span class="sxs-lookup"><span data-stu-id="186a9-169">On the orchestration Design view surface, click the **DoorbellSend** shape.</span></span>  
  
17. <span data-ttu-id="186a9-170">**プロパティ**] ウィンドウのドロップダウン リストで、**メッセージ**[ **DoorbellFinalMessage**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-170">In the **Properties** window, in the drop-down list for **Message**, select **DoorbellFinalMessage**.</span></span>  
  
18. <span data-ttu-id="186a9-171">緑色のハンドルをクリックして、 **SOAPReceivePort**の緑のハンドルにドラッグして、 **DoorbellReceive**受信図形の接続に、 **SOAPReceivePort** に**DoorbellReceive**図形を受信します。</span><span class="sxs-lookup"><span data-stu-id="186a9-171">Click the green handle in the **SOAPReceivePort** and drag it to the green handle on the **DoorbellReceive** receive shape to connect the **SOAPReceivePort** to the **DoorbellReceive** receive shape.</span></span>  
  
19. <span data-ttu-id="186a9-172">緑色のハンドルをクリックして、 **DoorbellSend**図形し、上の緑色のハンドルにドラッグ、 **MLLPSendPort**接続先のポート、 **DoorbellSend** に送信図形**MLLPSendPort**ポートです。</span><span class="sxs-lookup"><span data-stu-id="186a9-172">Click the green handle in the **DoorbellSend** shape and drag it to the green handle on the **MLLPSendPort** port to connect the **DoorbellSend** send shape to the **MLLPSendPort** port.</span></span>  
  
20. <span data-ttu-id="186a9-173">クリックして、**ソリューション エクスプ ローラー** ] タブの [オーケストレーションの種類。</span><span class="sxs-lookup"><span data-stu-id="186a9-173">Click the **Solution Explorer** tab under the Orchestration View.</span></span>  
  
21. <span data-ttu-id="186a9-174">ソリューション エクスプ ローラーで右クリック**BTAHL7V22Common**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="186a9-174">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Build**.</span></span> <span data-ttu-id="186a9-175">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="186a9-175">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="186a9-176">成功メッセージが表示されない場合は、ソリューションをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="186a9-176">If no success message appears, troubleshoot the solution.</span></span>  
  
22. <span data-ttu-id="186a9-177">右クリック**BTAHL7 プロジェクト**、 をクリック**展開**BTAHL7 プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="186a9-177">Right-click **BTAHL7 Project**, and click **Deploy** to deploy the BTAHL7 project.</span></span>  
  
 <span data-ttu-id="186a9-178">進みます[手順 14: オーケストレーション Web サービスとして公開](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="186a9-178">Proceed to [Step 14: Publish the Orchestration as a Web Service](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186a9-179">参照</span><span class="sxs-lookup"><span data-stu-id="186a9-179">See Also</span></span>  
 [<span data-ttu-id="186a9-180">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="186a9-180">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)