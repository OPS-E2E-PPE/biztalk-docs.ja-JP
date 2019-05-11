---
title: Sap Bapi に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b9fc9dc2d345d5f9a781759f26eb4a0126404b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373173"
---
# <a name="operations-on-bapis-in-sap"></a><span data-ttu-id="5fc4e-102">Sap Bapi に対する操作</span><span class="sxs-lookup"><span data-stu-id="5fc4e-102">Operations on BAPIs in SAP</span></span>
<span data-ttu-id="5fc4e-103">ビジネス アプリケーション プログラミング インターフェイス (BAPI) は、外部プロセスによって呼び出すことができる SAP ビジネス オブジェクトのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-103">A Business Application Programming Interface (BAPI) is a method of a SAP business object that can be called by an external process.</span></span> <span data-ttu-id="5fc4e-104">Bapi のでは、SAP システムでトランザクションです。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-104">BAPIs are transactional on the SAP system.</span></span>  
  
 <span data-ttu-id="5fc4e-105">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] BAPI を呼び出す送信方向でサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports BAPI calls in the outbound direction.</span></span> <span data-ttu-id="5fc4e-106">2 つの方法での Bapi が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-106">It surfaces BAPIs in two ways:</span></span>  
  
- <span data-ttu-id="5fc4e-107">**RFC として**します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-107">**As an RFC**.</span></span> <span data-ttu-id="5fc4e-108">適切な RFC を呼び出すことによって直接 BAPI を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-108">You can invoke a BAPI directly by invoking the appropriate RFC.</span></span>  
  
- <span data-ttu-id="5fc4e-109">**ビジネス オブジェクトのメソッドとして**します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-109">**As methods of business objects**.</span></span> <span data-ttu-id="5fc4e-110">アダプターのビジネス オブジェクト メソッドとしての Bapi のサーフェスを使用する場合は、メタデータを取得するのに役立つ便利な機能として、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-110">The adapter surfaces BAPIs as methods of business objects as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fc4e-111">RFC としてまたはビジネス オブジェクトのメソッドは、アダプターでの BAPI を呼び出すことができます。アダプターの BAPI の起動方法に関係なく常に呼び出します SAP の BAPI RFC インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-111">You can invoke a BAPI on the adapter as an RFC or as a method of a business object; but regardless of how you invoke the BAPI on the adapter, it always invokes the BAPI on SAP through the RFC interface.</span></span>  
  
 <span data-ttu-id="5fc4e-112">アダプターは、BAPI トランザクションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-112">The adapter supports BAPI transactions.</span></span> <span data-ttu-id="5fc4e-113">SAP の BAPI トランザクション モデルでは、いくつかの Bapi を作業 (LUW) の 1 つの論理単位に結合することができます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-113">The BAPI transaction model on SAP enables users to combine several BAPIs into one logical unit of work (LUW).</span></span> <span data-ttu-id="5fc4e-114">SAP、LUW は、データベースの更新を含むトランザクションに関連するすべての手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-114">An SAP LUW consists of all the steps involved in a transaction including updating the database.</span></span>  
  
 <span data-ttu-id="5fc4e-115">このセクションのトピックでは、ビジネス オブジェクトとしての Bapi の表示方法と、アダプターによって BAPI トランザクション (LUWs) をサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-115">The topics in this section explain how BAPIs are surfaced as business objects and how BAPI transactions (LUWs) are supported by the adapter.</span></span>  
 
  
## <a name="bapi-operations-as-business-object-methods"></a><span data-ttu-id="5fc4e-116">BAPI 操作 (としてビジネス オブジェクト メソッド)</span><span class="sxs-lookup"><span data-stu-id="5fc4e-116">BAPI Operations (as Business Object Methods)</span></span>  
 <span data-ttu-id="5fc4e-117">ビジネス オブジェクト メソッドを使用する場合は、メタデータを取得するのに役立つ便利なように、アダプター サーフェスの Bapi、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-117">The adapter surfaces BAPIs as business objects methods as a convenience to help you retrieve metadata when you use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="5fc4e-118">アダプターは、RFC インターフェイスを使用して SAP システムの Bapi を常に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-118">The adapter always invokes BAPIs on the SAP system using the RFC interface.</span></span>  
  
 <span data-ttu-id="5fc4e-119">アダプターは、名前での Bapi の送信操作の適切なビジネス オブジェクトの下の操作としては表示します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-119">The adapter surfaces BAPIs by name as operations under the appropriate business object for outbound operations.</span></span> <span data-ttu-id="5fc4e-120">ビジネス オブジェクトは、アダプターでの BAPI のカテゴリ ノードの下の機能グループによって収集されます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-120">Business objects are collected by functional group under the BAPI category node by the adapter.</span></span> <span data-ttu-id="5fc4e-121">(参照またはビジネス オブジェクトと Bapi を検索することができます、 **BAPI**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-121">(You can browse or search for business objects and BAPIs under the **BAPI** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="5fc4e-122">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Bapi に対する次のサポートします。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on BAPIs:</span></span>  
  
- <span data-ttu-id="5fc4e-123">インポート パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fc4e-123">IMPORT parameters</span></span>  
  
- <span data-ttu-id="5fc4e-124">パラメーターをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-124">EXPORT parameters</span></span>  
  
- <span data-ttu-id="5fc4e-125">変化するパラメーター</span><span class="sxs-lookup"><span data-stu-id="5fc4e-125">CHANGING parameters</span></span>  
  
- <span data-ttu-id="5fc4e-126">テーブル パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fc4e-126">Table parameters</span></span>  
  
  <span data-ttu-id="5fc4e-127">メッセージの構造と Bapi のビジネス オブジェクト メソッドとして表示するための SOAP アクションの詳細については、次を参照してください。 [BAPI 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-127">For more information about the message structures and SOAP actions used for BAPIs surfaced as business object methods, see [Message Schemas for BAPI Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).</span></span>  
  
## <a name="bapi-transactions"></a><span data-ttu-id="5fc4e-128">BAPI トランザクション</span><span class="sxs-lookup"><span data-stu-id="5fc4e-128">BAPI Transactions</span></span>  
 <span data-ttu-id="5fc4e-129">BAPI を呼び出すと、LUW で SAP システムの一部では常にします。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-129">When you invoke a BAPI, it is always part of an LUW on the SAP system.</span></span> <span data-ttu-id="5fc4e-130">これは、機能は、RFC としてまたはビジネス オブジェクトのメソッドとして、BAPI を呼び出すかどうかに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-130">This is true whether you invoke the BAPI as an RFC or as a method of a business object.</span></span> <span data-ttu-id="5fc4e-131">RFC SDK では、同じ LUW の一部として同じ SAP 接続経由で送信されるすべての Bapi を扱います。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-131">The RFC SDK treats all BAPIs sent over the same SAP connection as part of the same LUW.</span></span> <span data-ttu-id="5fc4e-132">呼び出しの後にコミットするか、接続でトランザクションをロールバックして、[次へ] の BAPI 接続経由で送信された新しい LUW を開始します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-132">After a call to commit or roll back the transaction on a connection, the next BAPI sent over the connection begins a new LUW.</span></span>  
  
 <span data-ttu-id="5fc4e-133">BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK をコミットまたはトランザクションをロールバックして呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-133">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the transaction.</span></span> <span data-ttu-id="5fc4e-134">アダプターでは、これら 2 つの Bapi が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-134">The adapter surfaces these two BAPIs:</span></span>  
  
- <span data-ttu-id="5fc4e-135">RFC 操作として [基準] ノードの下。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-135">Under the Basis node as RFC operations.</span></span>  
  
- <span data-ttu-id="5fc4e-136">各ビジネス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-136">Under each business object.</span></span>  
  
  <span data-ttu-id="5fc4e-137">トランザクションでの Bapi を制御するには、ことすべて経由送信されます (コミットまたはトランザクションをロールバックする呼び出しを含む)、同じ SAP 接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-137">You control the BAPIs in a transaction by ensuring that they are all sent over the same SAP connection (including the call to commit or roll back the transaction).</span></span> <span data-ttu-id="5fc4e-138">これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-138">You can do this in:</span></span>  
  
- <span data-ttu-id="5fc4e-139">BizTalk ソリューションを使用して、 **ConnectionState**メッセージ コンテキスト プロパティを同じ接続を使用して、トランザクションでの Bapi を送信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-139">BizTalk Solutions by using the **ConnectionState** message context property to ensure that the BAPIs in a transaction are sent using the same connection.</span></span> <span data-ttu-id="5fc4e-140">このプロパティは、アダプターによって提示され、BizTalk オーケストレーションでメッセージを送信するための接続を明示的に制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-140">This property is surfaced by the adapter and provides you with explicit control over the connection used to send a message in a BizTalk orchestration.</span></span>  
  
   <span data-ttu-id="5fc4e-141">BizTalk Server を使用して BAPI トランザクションを実行するため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のメッセージ コンテキスト プロパティがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-141">For performing BAPI transactions using BizTalk Server, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
  |<span data-ttu-id="5fc4e-142">フィールド</span><span class="sxs-lookup"><span data-stu-id="5fc4e-142">Field</span></span>|<span data-ttu-id="5fc4e-143">説明</span><span class="sxs-lookup"><span data-stu-id="5fc4e-143">Description</span></span>|  
  |-----------|-----------------|  
  |<span data-ttu-id="5fc4e-144">OPEN</span><span class="sxs-lookup"><span data-stu-id="5fc4e-144">OPEN</span></span>|<span data-ttu-id="5fc4e-145">トランザクションの新しいチャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-145">Opens a new channel for the transaction.</span></span>|  
  |<span data-ttu-id="5fc4e-146">再利用します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-146">REUSE</span></span>|<span data-ttu-id="5fc4e-147">トランザクションの既存のチャネルを再利用します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-147">Reuse existing channel for the transaction.</span></span>|  
  |<span data-ttu-id="5fc4e-148">CLOSE</span><span class="sxs-lookup"><span data-stu-id="5fc4e-148">CLOSE</span></span>|<span data-ttu-id="5fc4e-149">トランザクションをコミットし、既存のチャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-149">Commit the transaction and close the existing channel.</span></span>|  
  |<span data-ttu-id="5fc4e-150">ABORT</span><span class="sxs-lookup"><span data-stu-id="5fc4e-150">ABORT</span></span>|<span data-ttu-id="5fc4e-151">トランザクションを中止し、既存のチャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-151">Abort the transaction and close the existing channel.</span></span>|  
  
   <span data-ttu-id="5fc4e-152">詳細については、次を参照してください。[で BizTalk Server を使用して SAP の BAPI トランザクションの実行](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-152">For more information, see [Run BAPI Transactions in SAP using BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5fc4e-153">設定することを確認、 **EnableBizTalkCompatibilityMode**BizTalk Server を使用してトランザクションを実行するときに、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-153">Make sure you set the **EnableBizTalkCompatibilityMode**binding property when performing transactions using BizTalk Server.</span></span>  
  
- <span data-ttu-id="5fc4e-154">トランザクションでの Bapi を同じ WCF クライアントを使用して送信されるようにすることで WCF サービス モデル ソリューション。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-154">WCF service model solutions by ensuring that the BAPIs in a transaction are sent using the same WCF client.</span></span> <span data-ttu-id="5fc4e-155">詳細については、次を参照してください。 [WCF サービス モデルを使用して SAP の Bapi を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-155">For more information, see [Invoke BAPIs in SAP using WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="5fc4e-156">WCF チャネル モデル ソリューションにより、同じ WCF チャネル経由で送信されるトランザクションでの Bapi します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-156">WCF channel model solutions by ensuring that the BAPIs in a transaction are sent over the same WCF channel.</span></span> <span data-ttu-id="5fc4e-157">詳細については、次を参照してください。 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-157">For more information, see [Develop applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>  
  
### <a name="limitations-on-bapi-transactions"></a><span data-ttu-id="5fc4e-158">BAPI トランザクションに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="5fc4e-158">Limitations on BAPI Transactions</span></span>  
 <span data-ttu-id="5fc4e-159">BAPI トランザクションで、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-159">The following restrictions apply on BAPI transactions:</span></span>  
  
- <span data-ttu-id="5fc4e-160">1 つ LUW 内の同じインスタンスで 2 つの書き込みアクセスを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-160">It is not possible to make two write accesses on the same instance within one LUW.</span></span> <span data-ttu-id="5fc4e-161">たとえば、注文を作成するを同じトランザクションで更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-161">For example, you cannot create an order and update it in the same transaction.</span></span>  
  
- <span data-ttu-id="5fc4e-162">BAPI トランザクションを使用して、実行するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、送信ポートの 1 つのホスト インスタンス上のすべてのメッセージを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-162">When performing BAPI a transaction using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], all the messages must be sent over a single host instance of the send port.</span></span>  
  
- <span data-ttu-id="5fc4e-163">インスタンスが作成、更新、または書き込み BAPI を使用して、削除場合、読み取り BAPI は BAPI の書き込みがコミットされるまで、最新のデータを表示できません。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-163">If an instance is created, updated, or deleted by using a write BAPI, a read BAPI cannot view the most recent data until the write BAPI is committed.</span></span>  
  
- <span data-ttu-id="5fc4e-164">呼び出す、LUW 外部クライアントでは、同じ SAP 接続で、LUW を含むすべての Bapi を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-164">An external client that invokes an LUW should call all the BAPIs that the LUW contains on the same SAP connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fc4e-165">Bapi 3.1 のリリースに属しているでは、その実装の一部として、COMMIT WORK を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-165">BAPIs that belong to Release 3.1 call COMMIT WORK as part of their implementation.</span></span> <span data-ttu-id="5fc4e-166">意味これら Bapi ことはできません、LUW での Bapi の他に含まれています (トランザクションをコミットする) ためです。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-166">This means that these BAPIs cannot be included with other BAPIs in an LUW (because they will commit the transaction).</span></span> <span data-ttu-id="5fc4e-167">詳細については、SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fc4e-167">For more information, see the SAP documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc4e-168">参照</span><span class="sxs-lookup"><span data-stu-id="5fc4e-168">See Also</span></span>  
 <span data-ttu-id="5fc4e-169">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="5fc4e-169">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>