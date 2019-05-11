---
title: チェックリスト:メッセージとインスタンス データ追跡 |Microsoft Docs
description: メッセージ、インスタンス、および BizTalk Server での成果物を追跡する場合のベスト プラクティス
ms.custom: ''
ms.date: 02/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4b5b614-23e5-4895-9c66-417b55dee43c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2b1add90497180f4b1665719d39d5b59b5b6e36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357443"
---
# <a name="checklist-message-and-instance-data-tracking"></a><span data-ttu-id="41727-103">チェックリスト:メッセージとインスタンス データ追跡</span><span class="sxs-lookup"><span data-stu-id="41727-103">Checklist: Message and Instance Data Tracking</span></span>

|<span data-ttu-id="41727-104">手順</span><span class="sxs-lookup"><span data-stu-id="41727-104">Step</span></span>|<span data-ttu-id="41727-105">リファレンス</span><span class="sxs-lookup"><span data-stu-id="41727-105">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="41727-106">セキュリティに関する考慮事項を追跡メッセージおよびサービス インスタンス データを確認します。</span><span class="sxs-lookup"><span data-stu-id="41727-106">Review the message and service instance data tracking  security considerations</span></span>|[<span data-ttu-id="41727-107">メッセージとインスタンス データの追跡のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="41727-107">Security Considerations for Message and Instance Data Tracking</span></span>](../core/security-considerations-for-message-and-instance-data-tracking.md)|  
|<span data-ttu-id="41727-108">メッセージとサービス インスタンス データの追跡のベスト プラクティスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="41727-108">Review the  message and service instance data tracking best practices</span></span>|[<span data-ttu-id="41727-109">メッセージとインスタンス データ追跡のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="41727-109">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)|  
|<span data-ttu-id="41727-110">すべてのメッセージ ボックス データベースで SQL Server エージェント サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41727-110">Ensure that the SQL Server Agent service is running on all MessageBox databases</span></span>|<span data-ttu-id="41727-111">SQL Server エージェントを使用すると、メッセージ追跡および WMI でメッセージ本文を取得したり、メッセージ ボックス データベースをクリーンアップするジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="41727-111">SQL Server Agent makes message bodies available message tracking and WMI, and enables you to run jobs to clean up the MessageBox databases.</span></span><br /><br /> <span data-ttu-id="41727-112">SQL Server エージェントおよび SQL Server エージェント サービスの詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41727-112">See SQL Server Books Online for more information about SQL Server Agent and the SQL Server Agent service.</span></span>|  
|<span data-ttu-id="41727-113">BizTalk Server 管理コンソール内のアイテムの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="41727-113">Configure tracking on artifacts in the BizTalk Server Administration Console</span></span>|[<span data-ttu-id="41727-114">オーケストレーションの追跡</span><span class="sxs-lookup"><span data-stu-id="41727-114">Orchestration tracking</span></span>](how-to-configure-tracking-for-an-orchestration.md)<br/>[<span data-ttu-id="41727-115">送信ポートの追跡</span><span class="sxs-lookup"><span data-stu-id="41727-115">Send port tracking</span></span>](how-to-configure-tracking-for-a-send-port.md)<br/>[<span data-ttu-id="41727-116">受信ポートの追跡</span><span class="sxs-lookup"><span data-stu-id="41727-116">Receive port tracking</span></span>](how-to-configure-tracking-for-a-receive-port.md)<br/>[<span data-ttu-id="41727-117">ポリシーの追跡</span><span class="sxs-lookup"><span data-stu-id="41727-117">Policy tracking</span></span>](how-to-configure-tracking-for-a-policy.md)<br/>[<span data-ttu-id="41727-118">追跡スキーマ</span><span class="sxs-lookup"><span data-stu-id="41727-118">Schema tracking</span></span>](how-to-configure-tracking-for-a-schema.md)<br/>[<span data-ttu-id="41727-119">パイプラインの追跡</span><span class="sxs-lookup"><span data-stu-id="41727-119">Pipeline tracking</span></span>](how-to-configure-tracking-for-a-pipeline.md)|  

## <a name="see-also"></a><span data-ttu-id="41727-120">参照</span><span class="sxs-lookup"><span data-stu-id="41727-120">See Also</span></span>  
 [<span data-ttu-id="41727-121">メッセージとインスタンス データ追跡のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="41727-121">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)
