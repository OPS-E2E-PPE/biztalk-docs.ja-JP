---
title: 操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定 |Microsoft Docs
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
ms.openlocfilehash: 015182a6b091ccbba7452df4c44ed4e4f45c336e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974683"
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="6f7b6-102">操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定</span><span class="sxs-lookup"><span data-stu-id="6f7b6-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
<span data-ttu-id="6f7b6-103">Microsoft[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]サーバーと一連のエンタープライズ アプリケーション統合 (EAI)、ツール、ビジネス プロセスを自動化し、ビジネス パートナーとの対話を促進することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f7b6-103">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="6f7b6-104">上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プラットフォーム、BTAHL7 は HL7 標準を使用して、施設の医療のアプリケーション統合を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="6f7b6-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="6f7b6-105">HL7 には、交換する、統合、および臨床試験の演習と管理の電子的な情報を取得するための標準が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f7b6-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="6f7b6-106">インターフェイスのユーザーのアナリストは、取引先、メッセージの受信確認、メッセージのバッチ処理、およびビジネス プロセスに必要なその他の詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f7b6-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="6f7b6-107">このセクションでは、効率的に監視および BTAHL7 アプリケーション環境を保持することができます、概念と手順の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6f7b6-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f7b6-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6f7b6-108">In This Section</span></span>  
  
-   [<span data-ttu-id="6f7b6-109">ログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="6f7b6-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="6f7b6-110">メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="6f7b6-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="6f7b6-111">検証設定</span><span class="sxs-lookup"><span data-stu-id="6f7b6-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   <span data-ttu-id="6f7b6-112">
  [MSH フィールドのオーバーライド](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)</span><span class="sxs-lookup"><span data-stu-id="6f7b6-112">[MSH Field Overrides](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)</span></span>  
  
-   [<span data-ttu-id="6f7b6-113">受信確認設定</span><span class="sxs-lookup"><span data-stu-id="6f7b6-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="6f7b6-114">拡張されたエンコードのサポート</span><span class="sxs-lookup"><span data-stu-id="6f7b6-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)