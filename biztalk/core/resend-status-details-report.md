---
title: "状態の詳細レポートを再送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbc9d44-9a9a-4272-a138-ebd126a9f809
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2335b10da205258f32a6676a6fee2a3ff32fef65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="resend-status-details-report"></a><span data-ttu-id="7ffd3-102">再送信状態詳細レポート</span><span class="sxs-lookup"><span data-stu-id="7ffd3-102">Resend Status Details Report</span></span>
<span data-ttu-id="7ffd3-103">この状態レポートには、パーティの AS2 受信者としてのパーティのプロパティで、MDN を受信しない場合は AS2 メッセージを再送信するように構成されているときに行われる再試行についての情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-103">This status report displays information on retry attempts made when the Party as AS2 Receiver properties of a party are configured to resend the AS2 message if an MDN is not received.</span></span>  
  
 <span data-ttu-id="7ffd3-104">AS2/MDN の状態レポート内のメッセージを右クリックし、をクリックしてこのレポートを表示する**信頼性の高いメッセージの状態の表示**です。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-104">You display this report by right-clicking on a message in the AS2/MDN status report, and then clicking **View Reliable Messaging Status**.</span></span> <span data-ttu-id="7ffd3-105">[再送信の状態の詳細] ページに、そのメッセージに対して行われた再送信の試みについての情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-105">The Resend Status Details page will then display information on the resend attempts made for this message.</span></span>  
  
 <span data-ttu-id="7ffd3-106">このレポートは選択した場合にのみ**MDN を受信しない場合は再送信 AS2 メッセージ**関連するパーティの AS2 メッセージの受信者のプロパティとしてのパーティにします。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-106">This report is only available if you have selected **Resend AS2 message if MDN not received** in the Party as AS2 Message Receiver properties for the related party.</span></span>  
  
 <span data-ttu-id="7ffd3-107">レポートでは、メッセージに対して行われた再試行についての情報が次のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-107">The report displays information on the retry attempts made for the message on the following pages:</span></span>  
  
|<span data-ttu-id="7ffd3-108">ページ</span><span class="sxs-lookup"><span data-stu-id="7ffd3-108">Page</span></span>|<span data-ttu-id="7ffd3-109">表示されるデータ</span><span class="sxs-lookup"><span data-stu-id="7ffd3-109">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="7ffd3-110">**全般**</span><span class="sxs-lookup"><span data-stu-id="7ffd3-110">**General**</span></span>|<span data-ttu-id="7ffd3-111">現在の送信試行および再送信構成のインデックス。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-111">The index of the current send attempt as well as the resend configuration.</span></span>|  
|<span data-ttu-id="7ffd3-112">**再送信履歴**</span><span class="sxs-lookup"><span data-stu-id="7ffd3-112">**Resend History**</span></span>|<span data-ttu-id="7ffd3-113">メッセージの送信試行の履歴。</span><span class="sxs-lookup"><span data-stu-id="7ffd3-113">A history of send attempts for the message.</span></span>|