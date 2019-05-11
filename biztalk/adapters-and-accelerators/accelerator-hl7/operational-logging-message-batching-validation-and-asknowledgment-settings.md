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
ms.openlocfilehash: 11d4588c1a8a2bd197651e1032db72a638f1d36b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290050"
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="18162-102">操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定</span><span class="sxs-lookup"><span data-stu-id="18162-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
<span data-ttu-id="18162-103">Microsoft[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]サーバーと一連のエンタープライズ アプリケーション統合 (EAI)、ツール、ビジネス プロセスを自動化し、ビジネス パートナーとの対話を促進することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="18162-103">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="18162-104">上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プラットフォーム、BTAHL7 は HL7 標準を使用して、施設の医療のアプリケーション統合を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="18162-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="18162-105">HL7 には、交換する、統合、および臨床試験の演習と管理の電子的な情報を取得するための標準が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18162-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="18162-106">インターフェイスのユーザーのアナリストは、取引先、メッセージの受信確認、メッセージのバッチ処理、およびビジネス プロセスに必要なその他の詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="18162-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="18162-107">このセクションでは、効率的に監視および BTAHL7 アプリケーション環境を保持することができます、概念と手順の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="18162-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18162-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="18162-108">In This Section</span></span>  
  
-   [<span data-ttu-id="18162-109">ログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="18162-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="18162-110">メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="18162-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="18162-111">検証設定</span><span class="sxs-lookup"><span data-stu-id="18162-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   [<span data-ttu-id="18162-112">MSH フィールドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="18162-112">MSH Field Overrides</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)  
  
-   [<span data-ttu-id="18162-113">受信確認設定</span><span class="sxs-lookup"><span data-stu-id="18162-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="18162-114">拡張されたエンコードのサポート</span><span class="sxs-lookup"><span data-stu-id="18162-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)