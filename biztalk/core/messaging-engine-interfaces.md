---
title: メッセージング エンジンのインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14241db3-edcf-4449-9ec8-2171a14496c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08b8d795b6df72f3e555f527e3d995cab1d288e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394526"
---
# <a name="messaging-engine-interfaces"></a><span data-ttu-id="769de-102">メッセージング エンジンのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="769de-102">Messaging Engine Interfaces</span></span>
<span data-ttu-id="769de-103">アダプターがメッセージング エンジンとの対話を許可するために使用できるパブリック インターフェイスが 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="769de-103">There are three public interfaces that adapters can use to allow interaction with the Messaging Engine.</span></span> <span data-ttu-id="769de-104">これらのインターフェイスについて、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="769de-104">These are outlined in the following sections.</span></span>  
  
## <a name="ibttransportproxy"></a><span data-ttu-id="769de-105">IBTTransportProxy</span><span class="sxs-lookup"><span data-stu-id="769de-105">IBTTransportProxy</span></span>  
 <span data-ttu-id="769de-106">アダプターは常に、独自のトランスポート プロキシを使用してメッセージング エンジンと対話します。</span><span class="sxs-lookup"><span data-stu-id="769de-106">Adapters always interact with the Messaging Engine by using their own transport proxy.</span></span> <span data-ttu-id="769de-107">トランスポート プロキシは、バッチの作成、メッセージ ファクトリの取得、エンジンへの分離受信者の登録などの処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="769de-107">The transport proxy is used for operations such as creating batches, getting the message factory, and registering isolated receivers with the engine.</span></span>  
  
## <a name="ibttransportbatch"></a><span data-ttu-id="769de-108">IBTTransportBatch</span><span class="sxs-lookup"><span data-stu-id="769de-108">IBTTransportBatch</span></span>  
 <span data-ttu-id="769de-109">このインターフェイスは、メッセージング エンジンによって定義され、メッセージのバッチに対して処理を実行する際にアダプターが使用するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="769de-109">This interface is provided by the Messaging Engine, and defines methods that adapters can use to operate on batches of messages.</span></span> <span data-ttu-id="769de-110">メッセージング エンジンは、バッチを非同期に処理します。</span><span class="sxs-lookup"><span data-stu-id="769de-110">The Messaging Engine processes batches asynchronously.</span></span>  
  
## <a name="ibtdtccommitconfirm"></a><span data-ttu-id="769de-111">IBTDTCCommitConfirm</span><span class="sxs-lookup"><span data-stu-id="769de-111">IBTDTCCommitConfirm</span></span>  
 <span data-ttu-id="769de-112">バッチに対して明示的な Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションを使用するアダプターは、このインターフェイスを使用して、トランザクションの結果をエンジンに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="769de-112">Adapters using explicit Microsoft Distributed Transaction Coordinator (MSDTC) transactions on batches must use this interface to notify the engine of the outcome of the transaction using this interface.</span></span>