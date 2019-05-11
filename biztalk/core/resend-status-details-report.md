---
title: 再送信状態詳細レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cbc9d44-9a9a-4272-a138-ebd126a9f809
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 877e09fcbc2c2dc54b6c4f8bd7fb77827387b134
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322105"
---
# <a name="resend-status-details-report"></a><span data-ttu-id="d6ed3-102">再送信状態詳細レポート</span><span class="sxs-lookup"><span data-stu-id="d6ed3-102">Resend Status Details Report</span></span>
<span data-ttu-id="d6ed3-103">この状態レポートには、MDN が受信されない場合は、AS2 メッセージを再送信するパーティの AS2 受信者のプロパティとしてのパーティが構成されている場合に行われる再試行についての情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-103">This status report displays information on retry attempts made when the Party as AS2 Receiver properties of a party are configured to resend the AS2 message if an MDN is not received.</span></span>  
  
 <span data-ttu-id="d6ed3-104">このレポートに表示するには、AS2/MDN の状態レポート内のメッセージを右クリックして**信頼性の高いメッセージングの状態の表示**します。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-104">You display this report by right-clicking on a message in the AS2/MDN status report, and then clicking **View Reliable Messaging Status**.</span></span> <span data-ttu-id="d6ed3-105">再送信状態詳細ページは、このメッセージの再送信の試行に情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-105">The Resend Status Details page will then display information on the resend attempts made for this message.</span></span>  
  
 <span data-ttu-id="d6ed3-106">このレポートは、使用できるは、選択した場合にのみ**MDN を受信しない場合は再送信 AS2 メッセージ**関連するパーティの AS2 メッセージの受信者のプロパティとしてのパーティにします。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-106">This report is only available if you have selected **Resend AS2 message if MDN not received** in the Party as AS2 Message Receiver properties for the related party.</span></span>  
  
 <span data-ttu-id="d6ed3-107">レポートには、次のページ上のメッセージに対して行われる再試行について情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-107">The report displays information on the retry attempts made for the message on the following pages:</span></span>  
  
|<span data-ttu-id="d6ed3-108">ページ</span><span class="sxs-lookup"><span data-stu-id="d6ed3-108">Page</span></span>|<span data-ttu-id="d6ed3-109">表示されるデータ</span><span class="sxs-lookup"><span data-stu-id="d6ed3-109">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="d6ed3-110">**全般**</span><span class="sxs-lookup"><span data-stu-id="d6ed3-110">**General**</span></span>|<span data-ttu-id="d6ed3-111">再送信の構成と同様に、現在の送信試行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-111">The index of the current send attempt as well as the resend configuration.</span></span>|  
|<span data-ttu-id="d6ed3-112">**履歴を再送信します。**</span><span class="sxs-lookup"><span data-stu-id="d6ed3-112">**Resend History**</span></span>|<span data-ttu-id="d6ed3-113">メッセージの送信試行の履歴。</span><span class="sxs-lookup"><span data-stu-id="d6ed3-113">A history of send attempts for the message.</span></span>|