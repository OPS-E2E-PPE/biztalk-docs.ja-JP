---
title: Repair and New Submission をメッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bc15351848fe68d6ef54c31fc6d58c075bb1c58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209986"
---
# <a name="message-repair-and-new-submission"></a><span data-ttu-id="33e97-102">Message Repair and New Submission</span><span class="sxs-lookup"><span data-stu-id="33e97-102">Message Repair and New Submission</span></span>
<span data-ttu-id="33e97-103">メッセージ修復 and New Submission 機能[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]MT および MX メッセージの検証に失敗を修復するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="33e97-103">The Message Repair and New Submission feature of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides a way for you to repair MT and MX messages that fail validation.</span></span> <span data-ttu-id="33e97-104">(ユーザーが展開されている) MRSR SharePoint サイトを使用して表示できます、メッセージが検証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="33e97-104">Using the MRSR SharePoint site (deployed by user), you can see how the message failed validation.</span></span> <span data-ttu-id="33e97-105">MRSR サイトからを使用すると、エラーを特定し、メッセージの修復、再処理のために送信する InfoPath フォームのメッセージを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="33e97-105">From MRSR site, you can open the message in an InfoPath form that enables you to identify the error, repair the message, and submit it for reprocessing.</span></span>  
  
 <span data-ttu-id="33e97-106">Message Repair and New Submission ロール ベースのメッセージの修復をサポートします。</span><span class="sxs-lookup"><span data-stu-id="33e97-106">Message Repair and New Submission supports role-based message repair.</span></span> <span data-ttu-id="33e97-107">完全修復ワークフローには、修復、確認、および承認が含まれています。</span><span class="sxs-lookup"><span data-stu-id="33e97-107">A full repair workflow includes repair, verification, and approval.</span></span> <span data-ttu-id="33e97-108">修復ワークフローは、ワークフローのロール (または段階) を定義し、各ロールに対して、A4SWIFT ユーザーを構成する部門に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="33e97-108">A repair workflow is associated with a department that defines the roles (or stages) of the workflow and configures an A4SWIFT user for each role.</span></span> <span data-ttu-id="33e97-109">各修復ロールには、ロールに合わせて個別 MRSR サイト ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="33e97-109">Each repair role has a separate MRSR site view tailored to the role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="33e97-110">検証、および各 A4SWIFT を実行するユーザー ロール記号、メッセージ セキュリティで保護された処理を行うため、証明書の使用を実行します。</span><span class="sxs-lookup"><span data-stu-id="33e97-110"> performs validation, and each A4SWIFT user performing a role signs the message, using a certificate, to ensure a secure process.</span></span>  
  
 <span data-ttu-id="33e97-111">メッセージの修復に加えて A4SWIFT を使用すると、拡張を使用して、新しいメッセージを送信する[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。</span><span class="sxs-lookup"><span data-stu-id="33e97-111">In addition to message repair, A4SWIFT enables you to submit a new message using an enhanced [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="33e97-112">4 番目の A4SWIFT ユーザーの作成者は、この関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="33e97-112">A fourth A4SWIFT user, a creator, performs this function.</span></span> <span data-ttu-id="33e97-113">また、プロセスは、検証を実行し、送信が成功したことを確認する修復、確認、および承認のロールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="33e97-113">The process also performs validation, and can involve repair, verification, and approval roles to ensure successful submission.</span></span> <span data-ttu-id="33e97-114">A4SWIFT ハンドルから新しいメッセージの送信、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]修復されたメッセージを処理する同じ方法を形成します。</span><span class="sxs-lookup"><span data-stu-id="33e97-114">A4SWIFT handles new message submission through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form the same way that it handles a repaired message.</span></span>  
  
 <span data-ttu-id="33e97-115">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="33e97-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="33e97-116">メッセージの修復処理</span><span class="sxs-lookup"><span data-stu-id="33e97-116">Message Repair Process</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [<span data-ttu-id="33e97-117">Message Repair and New Submission の部門とロールの作成</span><span class="sxs-lookup"><span data-stu-id="33e97-117">Creating Departments and Roles for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="33e97-118">InfoPath フォームを使用してメッセージを修復または、新しいメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="33e97-118">Using an InfoPath Form to Repair a Message or Submit a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [<span data-ttu-id="33e97-119">Message Repair and New Submission の特別な処理</span><span class="sxs-lookup"><span data-stu-id="33e97-119">Special Processing in Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="33e97-120">未解析のメッセージの修復</span><span class="sxs-lookup"><span data-stu-id="33e97-120">Repairing Unparsed Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [<span data-ttu-id="33e97-121">Message Repair and 新しい送信サービスの処理</span><span class="sxs-lookup"><span data-stu-id="33e97-121">Message Repair and New Submission Service Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)