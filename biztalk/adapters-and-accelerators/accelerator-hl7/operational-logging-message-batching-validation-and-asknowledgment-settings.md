---
title: 運用上のログ記録、メッセージのバッチ処理、検証、および asknowledgment 設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, administering
- managing
- BTAHL7, managing
- administering
ms.assetid: c7376de4-4e1d-47e2-acf7-0a32e7a4b073
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3282d69fc572c4aa32888f9a3ed8a806deef5c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206002"
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="ee796-102">運用上のログ記録、メッセージのバッチ処理、検証および asknowledgment 設定</span><span class="sxs-lookup"><span data-stu-id="ee796-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="ee796-103">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]サーバーと一連のエンタープライズ アプリケーション統合 (EAI) のツールのビジネス プロセスを自動化して、ビジネス パートナーとの対話を容易にすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee796-103"> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="ee796-104">上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プラットフォーム、BTAHL7 HL7 標準を使用して、機能の医療アプリケーション統合を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="ee796-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="ee796-105">HL7 には、交換する、統合、および治療プラクティスおよび管理の電子情報を取得するための標準が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee796-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="ee796-106">インターフェイスのユーザーのアナリストは、取引先、メッセージの受信確認、メッセージがバッチ処理、およびビジネス プロセスを必要とするその他の詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="ee796-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="ee796-107">このセクションを効果的に監視し、BTAHL7 アプリケーション環境の管理を有効にする概念および手順に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ee796-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee796-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee796-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ee796-109">ログの構成</span><span class="sxs-lookup"><span data-stu-id="ee796-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="ee796-110">メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="ee796-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="ee796-111">検証の設定</span><span class="sxs-lookup"><span data-stu-id="ee796-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   [<span data-ttu-id="ee796-112">MSH フィールドの上書き</span><span class="sxs-lookup"><span data-stu-id="ee796-112">MSH Field Overrides</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)  
  
-   [<span data-ttu-id="ee796-113">確認の設定</span><span class="sxs-lookup"><span data-stu-id="ee796-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="ee796-114">エンコードのサポートを拡張</span><span class="sxs-lookup"><span data-stu-id="ee796-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)