---
title: 有効にするパイプラインの追跡 |Microsoft Docs
description: メッセージ本文の追跡と、パイプラインが BizTalk Server でメッセージを処理するときのイベント
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689d5395d75a558e3f437c4a3efea13c70f593e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385878"
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a>パイプラインが BizTalk Server での追跡を構成します。
パイプラインの追跡を構成するのにには、BizTalk Server 管理コンソールを使用します。 トラブルシューティングと監査のための追跡を構成する場合があります。 メッセージ プロパティ、ポート イベント、およびメッセージ イベントを表示することができます。 メッセージ イベントおよびポート イベント メッセージを追跡することもできます。  
  
 含まれている既定のパイプラインのいずれかの追跡を構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または BizTalk アプリケーションに展開されているカスタム パイプラインです。 構成する追跡の設定は、すべてのパイプラインのインスタンスに適用されます。  
  
> [!IMPORTANT]
>  パイプラインの追跡を構成することができます、このパイプラインを使用しているすべてのポートに対してデータをグローバルに収集されたため、大量のデータが生成されます。 代わりに、推奨を送信の追跡を構成し、受信ポート、」の説明に従って[送信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-send-port.md)と[受信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-receive-port.md)します。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>前提条件  
BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="enable-pipeline-tracking"></a>パイプラインの追跡を有効にします。
  
1.  **BizTalk Server 管理**パイプラインが含まれている BizTalk グループを展開します。 
  
2.  次のいずれかの操作を行います。  
  
    -   既定値のいずれかの BizTalk パイプラインの追跡を構成するには、展開\<すべての成果物\>します。  
  
    -   BizTalk アプリケーションに展開されているカスタム パイプラインの追跡を構成するには、パイプラインを含むアプリケーションを展開します。  
  
3.  選択、**パイプライン**フォルダーは、パイプラインを右クリックし、**追跡**します。  
  
    > [!NOTE]
    >  複数のパイプラインを一度に、Shift キーを押しながら選択を構成するには、各パイプラインの追跡を構成するにはパイプラインの 1 つを右クリックし、**追跡**します。  
  
4.  次の詳細を使用し、クリックして追跡オプションを構成する**OK**変更を保存します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**イベントの追跡 - ポートの開始し、終了イベント**|インスタンスが開始し、終了時点のみを追跡します。 詳細についてには、項目の名前、アセンブリ、およびその他のメタデータが含まれます。|  
    |**イベントの追跡 - メッセージの送信および受信イベント**|追跡メッセージの送信およびイベントを受信します。 場合にのみ利用できます**ポートの開始と終了イベントのイベント**が選択されています。|  
    |**メッセージ本文の追跡のパイプライン処理前に、のメッセージ**|保存し、Url などのメタデータを保持し、昇格させたプロパティと、パイプラインで受信メッセージの本文を追跡します。 受信パイプラインの場合は、トランスポート コンポーネントによって、パイプラインに送信されると、メッセージ本文、生のメッセージです。 アプリケーションによっては、メッセージ可能性がある暗号化、署名済み、またはエンコードします。 受信パイプラインを BizTalk マップを使用する場合は、受信マップが処理された後に追跡が実行されます。<br /><br /> 場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。|  
    |**メッセージ本文の追跡のパイプライン処理後のメッセージ**|保存し、Url などのメタデータを保持し、昇格させたプロパティと、パイプラインによって送信されたメッセージ本文を追跡します。 受信パイプラインの場合は、メッセージ本文は、アプリケーションによっては XML である可能性がありますが、メッセージ ボックス データベースへの送信処理されたメッセージです。 送信パイプラインは、この場合は、BizTalk マップを使用している場合は、送信マップが処理される前に追跡が実行されます。<br /><br /> 場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。|  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)
