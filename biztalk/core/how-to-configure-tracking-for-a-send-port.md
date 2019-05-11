---
title: 送信ポートの追跡を有効にする |Microsoft Docs
description: メッセージ本文の追跡をオンにし、BizTalk server 送信ポートでメッセージ プロパティの追跡
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
ms.openlocfilehash: 578d48c5eefe4866de974b11f1171cf271a24156
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385987"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a>BizTalk server 送信ポートの追跡を構成します。
使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをメッセージ本文や昇格させたプロパティを表示するオプションなどの追跡、送信ポートを構成します。 これにより、BizTalk 実装の正常性を監視し、ボトルネックを識別できます。 構成する追跡の設定は、すべての送信ポートのインスタンスに適用されます。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="enable-tracking-on-a-send-port"></a>送信ポートの追跡を有効にします。  
  
1.  **BizTalk Server 管理**、BizTalk グループを展開し、送信ポートを含む BizTalk アプリケーションを展開します。  
  
2.  選択**送信ポート**、送信ポートを右クリックし、選択**プロパティ**、し、**追跡**します。  
  
    > [!NOTE]
    >  1 つの送信ポートは、1 つだけ送信パイプラインを関連付けることができます。 送信パイプラインでメッセージ本文の追跡が無効の場合は、送信ポートで追跡されますが何も。 このようなシナリオで無効にする「追跡」オプションでその送信ポート。  
  
3.  次の詳細を使用し、クリックして追跡オプションを有効に**OK**変更を保存します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**|保存し、メッセージを受信する前に、メッセージの内容を追跡します。 <br/><br/> **注**:メッセージ本文パイプラインの追跡をポート処理前に、の応答メッセージを正常に追跡を有効にすることを確認します。|  
    |**メッセージ本文の追跡 - ポート処理後の要求メッセージ**|保存し、メッセージが受信された後メッセージの内容を追跡します。|  
    |**メッセージ本文 – ポート処理前に、の応答メッセージの追跡します。**|保存し、メッセージが送信される前に、メッセージの内容を追跡します。 送信請求-応答送信ポートでのみ使用できます。|    
    |**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**|保存し、メッセージが送信された後、メッセージの内容を追跡します。 送信請求-応答送信ポートでのみ使用できます。|  
    |**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**|受信メッセージの昇格させたプロパティを追跡します。|  
    |**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**|送信メッセージの昇格させたプロパティを追跡します。|  
    |**メッセージのプロパティ-ポート処理前に、の応答メッセージの追跡します。**|保存し、メッセージが送信される前に、メッセージのプロパティを追跡します。 送信請求-応答送信ポートでのみ使用できます。|   
    |**メッセージのプロパティ – ポート処理後の応答メッセージの追跡します。**|保存し、メッセージが送信された後にプロパティを追跡します。 送信請求-応答送信ポートでのみ使用できます。|   
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)
