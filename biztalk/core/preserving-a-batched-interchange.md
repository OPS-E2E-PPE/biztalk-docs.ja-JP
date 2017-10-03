---
title: "バッチ インターチェンジの保存 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7ea2bdef1fe2b2c3db92421d610b0b889e0460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="preserving-a-batched-interchange"></a>バッチ インターチェンジの保存
このトピックでは、バッチ EDI インターチェンジのトランザクション セットを分割せずに、インターチェンジを 1 つのドキュメントとして処理するアグリーメントの構成方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a>保存されたバッチの送受信を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。 **パーティとビジネス プロファイル** ページで、そのパーティが受信したバッチ インターチェンジに解決されるアグリーメントをクリックします。 **アグリーメント**セクションで、ページのアグリーメントを右クリックし、をクリックして**プロパティ**です。 **アグリーメントのプロパティ**ダイアログ ボックスで、(受信のバッチ インターチェンジが解決先) の一方向アグリーメント タブで、次の操作します。  
  
    1.  **識別子** ページで、ISA5、ISA6、ISA7、および ISA8 の値を入力の値を入力します。 受信したバッチ処理インターチェンジがこのアグリーメントに解決されるように、正しい値を入力してください。  
  
    2.  **ローカル ホストの設定**ページ (**インターチェンジの設定**) **受信者の設定** セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。  
  
        -   **インターチェンジの保存 - エラーでインターチェンジを中断**– こと BizTalk Server は、インターチェンジはそのまま残す、バッチ インターチェンジ全体に対して XML ドキュメントを作成するを指定するには、このオプションを選択します。 このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server がインターチェンジ全体を保留するようになります。  
  
        -   **インターチェンジの保存 - エラーのトランザクション セットを中断**– こと BizTalk Server は、インターチェンジはそのまま残す、バッチ インターチェンジ全体に対して XML ドキュメントを作成するを指定するには、このオプションを選択します。 このオプションを使用して、インターチェンジ内の 1 つまたは複数のトランザクション セットには、検証が失敗した場合に BizTalk Server は中断そのトランザクション セットのみ、その他のすべてのトランザクション セットの処理を継続します。  
  
        > [!NOTE]
        >  上記 2 つのオプションのいずれか 1 つをオンにした場合、インターチェンジ、グループ、およびトランザクション セット セグメントのプロパティ (BizTalk Server で送信インターチェンジの ISA、GS、ST のヘッダーをどのように作成するかを決定します) は適用されません。 保存されるインターチェンジに含まれているインターチェンジ、グループ、およびトランザクション セットの各ヘッダーは、送信パイプラインがインターチェンジの送信処理を行うときに保持されます。 しかし、アグリーメントでインターチェンジに指定された値を使用する場合、`EDI.PopulateInterchangeValues` コンテクスト プロパティを true に設定します。  
  
2.  保存されたバッチの Visual Studio プロジェクトを次のように作成します。  
  
    1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージ用のスキーマを追加します。  
  
    2.  プロジェクトをビルドし、配置します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、保存されたバッチを送信するための送信ポートを次のように作成します。  
  
    1.  送信パイプラインに設定**EdiSend**または**AS2EdiSend**です。  
  
    2.  送信ポートのフィルターをコンテキスト プロパティ `EDI.ReuseEnvelope == True` に設定します。  
  
        > [!NOTE]
        >  このフィルターを設定すると、保存されているすべてのバッチ インターチェンジに送信ポートがサブスクライブされます。 EdiReceive 受信パイプラインは、インターチェンジを保存されたインターチェンジとして識別するために、コンテキスト プロパティ `EDI.ReuseEnvelope` を昇格させます。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)