---
title: 送信ポートと送信ポート グループの管理 |Microsoft Docs
description: リンクを作成するには、構成、参加、参加解除、および開始し、停止の BizTalk Server での送信ポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db45f9f9-b32a-4b9c-a3bf-8c271d0f0cf9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3512a9ab6d3ef7995ee576be0528878588753c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380185"
---
# <a name="manage-send-ports-and-send-port-groups"></a>送信ポートと送信ポート グループを管理します。

## <a name="overview"></a>概要
このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションの送信ポートおよび送信ポート グループを作成、構成、および管理する方法について説明します。 送信ポートは、メッセージの送信先や、場合によっては応答の受信先となる場所を指定します。 送信ポートのサービスの新しいインスタンスを作成すると、送信ポートにメッセージが送信されると呼ばれる時間を*サービス インスタンス*します。  
  
 送信ポート グループは、送信ポートの論理的な集まりです。 1 つの送信ポート グループに送信されたメッセージは、関連するすべての送信ポートに送信されます。  送信ポートおよび送信ポート グループの背景については、次を参照してください。[送信ポートと送信ポート グループ](../core/send-ports-and-send-port-groups.md)します。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
> 
> [!NOTE]
>  BizTalk アプリケーションの開発中に、オーケストレーション デザイナーなど、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk デザイン ツールを使用して、送信ポートおよび送信ポート グループを作成および構成することができます。 詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)  
  
-   [送信ポート グループの作成および構成](../core/creating-and-configuring-send-port-groups.md)  
  
-   [送信ポートまたは送信ポート グループの登録](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [送信ポートまたは送信ポート グループの登録解除](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [送信ポートまたは送信ポート グループを開始する](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [送信ポートまたは送信ポート グループを停止する](../core/how-to-stop-a-send-port-or-send-port-group.md)