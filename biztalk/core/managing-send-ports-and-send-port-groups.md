---
title: 送信ポートと送信ポート グループの管理 |Microsoft ドキュメント
description: リンクを作成、構成、参加、参加解除、および開始し、停止の BizTalk Server での送信ポート
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
ms.openlocfilehash: 928160ed5b67602c8fc8d9d646459bf2425d7a01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262706"
---
# <a name="manage-send-ports-and-send-port-groups"></a>送信ポートと送信ポート グループを管理します。

## <a name="overview"></a>概要
このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションの送信ポートおよび送信ポート グループを作成、構成、および管理する方法について説明します。 送信ポートは、メッセージの送信先や、場合によっては応答の受信先となる場所を指定します。 呼び出される送信ポート サービスの新しいインスタンスを作成すると、送信ポートにメッセージが送られるたび、*サービス インスタンス*です。  
  
 送信ポート グループは、送信ポートの論理的な集まりです。 1 つの送信ポート グループに送信されたメッセージは、関連するすべての送信ポートに送信されます。  送信ポートおよび送信ポート グループに関する背景情報については、次を参照してください。[送信ポートおよび送信ポート グループ](../core/send-ports-and-send-port-groups.md)です。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
> [!NOTE]
>  BizTalk アプリケーションの開発中に、オーケストレーション デザイナーなど、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk デザイン ツールを使用して、送信ポートおよび送信ポート グループを作成および構成することができます。 詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)です。  
  
## <a name="next-steps"></a>次の手順
  
-   [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)  
  
-   [作成して、送信ポート グループを構成します。](../core/creating-and-configuring-send-port-groups.md)  
  
-   [送信ポートまたは送信ポート グループを参加させる](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [送信ポートまたは送信ポート グループを参加解除します。](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [送信ポートまたは送信ポート グループを開始します。](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [送信ポートまたは送信ポート グループを停止します。](../core/how-to-stop-a-send-port-or-send-port-group.md)