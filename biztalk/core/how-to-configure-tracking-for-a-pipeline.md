---
title: "パイプラインの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [pipelines], tracking warning
- tracking, pipelines
- tracking, warnings
- configuring, pipelines
- pipelines, tracking
- managing [pipelines], configuring
- tracking, configuring
- pipelines, configuring
- configuring [HAT tracking], pipelines
- HAT, pipelines
- managing [pipelines], tracking
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e933e9b50c99e11013ceaedf65c4f253ad1620c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-pipeline"></a>パイプラインの追跡を構成する方法
このトピックでは、BizTalk Server 管理を使用して、パイプラインの追跡を構成する方法について説明します。 追跡は、トラブルシューティングと監査のために構成できます。 メッセージ プロパティ、ポート イベント、およびメッセージ イベントを表示できます。 メッセージのメッセージ イベントおよびポート イベントも追跡できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれている既定のパイプラインの 1 つ、または BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成できます。 構成する追跡の設定は、パイプラインのすべてのインスタンスに適用されます。  
  
> [!IMPORTANT]
>  パイプラインの追跡を構成することはできますが、パイプラインを追跡すると、パイプラインを使用するすべてのポートのデータがグローバルに収集されるので、大量のデータが生成されます。 お勧め代わりに、送信の追跡を構成し、受信ポート、」の説明に従って[送信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-send-port.md)と[受信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-receive-port.md)です。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-tracking-for-a-pipeline"></a>パイプラインの追跡を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**の追跡を構成するパイプラインを含む BizTalk グループを展開します。  
  
3.  次のいずれかの操作を行います。  
  
    -   既定値のいずれかの BizTalk パイプラインの追跡を構成するのには、展開\<すべてのアイテム >。  
  
    -   BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成する場合は、パイプラインが含まれているアプリケーションを展開します。  
  
4.  クリックして、**パイプライン**フォルダーは、パイプラインを右クリックし、をクリックして**追跡**です。  
  
    > [!NOTE]
    >  複数のパイプラインを一度に、Shift キーを押しながらクリックを構成するのには、各パイプラインの追跡を構成するのに、パイプラインの 1 つを右クリックして**追跡**です。  
  
5.  次の表の説明に従って、必要な追跡オプションを構成し、をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ポートの開始と終了イベント**|インスタンスの開始時と終了時のみを追跡する場合に、このチェック ボックスをオンにします。 [詳細] には、項目名、アセンブリ、および他のメタデータが含まれます。|  
    |**メッセージの送信および受信イベント**|メッセージの送信イベントと受信イベントを追跡する場合は、このチェック ボックスをオンにします。 このチェック ボックスは使用可能な場合にのみ、**ポートの開始と終了イベント**が選択されています。|  
    |**パイプライン処理前に、のメッセージ**|パイプラインで受信されたメッセージ本文を保存および追跡する場合に、このチェック ボックスをオンにします。このパイプラインでは、URL や昇格させたプロパティなどのメタデータが保持されます。 パイプラインが受信パイプラインの場合、このメッセージ本文は、トランスポート コンポーネントからパイプラインに送信される時点の未処理のメッセージです。 アプリケーションによっては、メッセージは暗号化、署名、またはエンコードされていることがあります。 BizTalk マップを使用するときに、これが受信パイプラインである場合は、追跡は受信マップが処理された後で行われます。<br /><br /> このチェック ボックスは使用可能な場合にのみ、**メッセージの送信および受信イベント**が選択されています。|  
    |**パイプライン処理後のメッセージ**|パイプラインで送信されたメッセージ本文を保存および追跡する場合に、このチェック ボックスをオンにします。このパイプラインでは、URL や昇格させたプロパティなどのメタデータが保持されます。 パイプラインが受信パイプラインの場合、このメッセージ本文は、メッセージ ボックス データベースに送信される時点の処理済みのメッセージです。アプリケーションによっては XML 形式である場合があります。 BizTalk マップを使用するときに、これが送信パイプラインである場合は、追跡は送信マップが処理される前に行われます。<br /><br /> このチェック ボックスは使用可能な場合にのみ、**メッセージの送信および受信イベント**が選択されています。|  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)