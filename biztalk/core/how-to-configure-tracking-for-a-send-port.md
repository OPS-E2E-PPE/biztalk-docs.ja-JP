---
title: 送信ポートの追跡を有効にする |Microsoft ドキュメント
description: メッセージ本文の追跡を有効にし、BizTalk Server での送信ポートでメッセージ プロパティの追跡
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 223c417769086cc71f501b044410bf2d3e4cbc74
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2017
ms.locfileid: "26686633"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a>BizTalk Server で送信ポートの追跡を構成します。
使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをメッセージ本文や昇格させたプロパティを表示するオプションなどの送信ポートの追跡を構成します。 これにより、BizTalk 実装の稼動状況を監視し、ボトルネックを識別できます。 構成する追跡の設定は、送信ポートのすべてのインスタンスに適用されます。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>Prerequisites  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="enable-tracking-on-a-send-port"></a>送信ポートの追跡を有効にします。  
  
1.  **BizTalk Server 管理コンソール**し、BizTalk グループを展開し、送信ポートのある BizTalk アプリケーションの順に展開します。  
  
2.  選択**送信ポート**、送信ポートを右クリックし、選択**プロパティ**、し、**追跡**です。  
  
    > [!NOTE]
    >  1 つの送信ポートは 1 つの送信パイプラインにのみ関連付けることができます。 送信パイプラインでメッセージ本文の追跡が無効な場合は、送信ポートで追跡されますが何も行われません。 そのようなシナリオでは、その送信ポートで [追跡] オプションを無効にできます。  
  
3.  選択し、追跡オプションを有効にする、次の情報を使用して**OK**して変更を保存します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**|保存し、メッセージを受信する前に、メッセージの内容を追跡します。 <br/><br/> **注**: メッセージ本文パイプラインの追跡をポート処理前に、の応答メッセージを正常に追跡を有効にしてください。|  
    |**メッセージ本文の追跡 - ポート処理後の要求メッセージ**|保存し、メッセージを受信した後、メッセージの内容を追跡します。|  
    |**メッセージ本文 – ポート処理前に、の応答メッセージの追跡します。**|保存し、メッセージが送信される前に、メッセージの内容を追跡します。 送信請求-応答送信ポートでのみ使用できます。|    
    |**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**|保存し、メッセージが送信された後に、メッセージの内容を追跡します。 送信請求-応答送信ポートでのみ使用できます。|  
    |**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**|受信メッセージの昇格させたプロパティを追跡します。|  
    |**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**|送信メッセージの昇格させたプロパティを追跡します。|  
    |**メッセージのプロパティ-ポート処理前に、の応答メッセージの追跡します。**|保存し、メッセージが送信される前に、メッセージのプロパティを追跡します。 送信請求-応答送信ポートでのみ使用できます。|   
    |**メッセージのプロパティ – ポート処理後の応答メッセージの追跡します。**|保存し、メッセージが送信された後にプロパティを追跡します。 送信請求-応答送信ポートでのみ使用できます。|   
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)
