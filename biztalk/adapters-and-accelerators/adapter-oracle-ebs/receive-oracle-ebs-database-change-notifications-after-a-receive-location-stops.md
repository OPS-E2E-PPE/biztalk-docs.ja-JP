---
title: 受信場所のブレーク ダウンの後に Oracle E-business Suite データベースの変更通知を受け取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12c42cd0-b46e-4c45-a67e-e1fb9c0e8a6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64a451c173bd64f7650882ac77fa42873ab840dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216138"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-after-a-receive-location-breakdown"></a>受信場所のブレーク ダウンの後に Oracle E-business Suite データベースの変更通知を受信します。
ACCOUNTACTIVITY テーブルへの変更が加えられたときに、データベース変更の通知メッセージを受信する BizTalk アプリケーションが存在するシナリオを検討してください。 一部として、受信場所が構成されている場合、BizTalk アプリケーションが分割すると、同時に ACCOUNTACTIVITY テーブルにレコードを追加、最近追加されたレコードの通知を受け取ることはできません。 わからない場合、受信場所が再び使用可能。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド プロパティを公開**NotifyOnListenerStart**、されるを取得する通知が受信場所の回復を構成することができます。 次の値を指定することができます、 **NotifyOnListenerStart**プロパティをバインドします。  
  
-   このプロパティを設定**True**、受信場所が使用できる、受信場所を復旧するとすぐに知らせる通知を受信します。  
  
-   このプロパティを設定**False**、受信場所は、受信場所の回復後、使用可能な通知の通知を受信しません。  
  
 既定値は**True**です。  
  
## <a name="configuring-the-oracle-e-business-adapter-behavior"></a>Oracle E-business アダプターの動作を構成します。  
 アプローチのいずれか、メタデータの生成中に、または BizTalk アプリケーションを構成するときに、特定のタスクを実行する必要はありません。 のみを設定する必要があります、 **NotifyOnListenerStart**適宜 Wcf-custom または Wcf-oracleebs で受信場所にプロパティをバインドします。 BizTalk アプリケーションを作成する」の説明に従って、同じ一連のタスクを実行する必要があります[受信 Oracle E-business Suite 変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)です。 ただし、BizTalk アプリケーションを使用して、構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を変更しようとすることができます**NotifyOnListenerStart** binding プロパティと、2 つの構成の違いを確認します。  
  
 次の図は、通知の値に基づいて受信方法を示しています、 **NotifyOnListenerStart**プロパティをバインドします。  
  
 ![通知の SQL アダプターを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 最初のシナリオでは、ことに注意してくださいときに、 **NotifyOnListenerStart**に設定されている**True**受信場所がダウンしたときに、データベース テーブルにレコードを挿入、アダプターにのみ送信すると、。受信場所が表示されたら、メッセージを通知します。 アダプター受信場所が停止していた間に挿入されたレコードを処理する任意の操作は実行されません。 アダプター クライアントは、受信場所が停止していた間に挿入されたレコードを処理するには、そのアプリケーション内で関連するロジックを実装する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle E-business Suite データベースの変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)