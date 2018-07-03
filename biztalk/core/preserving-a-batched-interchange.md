---
title: バッチ インターチェンジの保存 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 907e07f3-1f3e-485e-a82d-b28eb7658e0a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 887995e9a44996c57da9e36bec1c5ec3edc1cc7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993491"
---
# <a name="preserving-a-batched-interchange"></a>バッチ インターチェンジの保存
このトピックでは、バッチ EDI インターチェンジのトランザクション セットを分割せずに、インターチェンジを 1 つのドキュメントとして処理するアグリーメントの構成方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a>保存されたバッチの送受信を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。 **パーティとビジネス プロファイル** ページで、受信したバッチ インターチェンジを解決するアグリーメントのパーティをクリックします。 **契約**セクション、ページのアグリーメントを右クリックし、をクリックして**プロパティ**します。 **アグリーメントのプロパティ**ダイアログ ボックスの一方向アグリーメント タブ (受信のバッチ インターチェンジが解決先) で、次の操作を行います。  
  
   1.  **識別子** ページで、ISA5、ISA6、ISA7、および ISA8 の値を入力の値を入力します。 受信したバッチ処理インターチェンジがこのアグリーメントに解決されるように、正しい値を入力してください。  
  
   2.  **ローカル ホスト設定**ページ (**インターチェンジの設定**) 下で、**受信者の設定**セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。  
  
       -   **インターチェンジの保存 - エラーでインターチェンジを中断**– BizTalk Server がままにするインターチェンジ、バッチ インターチェンジ全体に対して XML ドキュメントを作成するかを指定するには、このオプションを選択します。 このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server がインターチェンジ全体を保留するようになります。  
  
       -   **インターチェンジの保存 - エラーのトランザクション セットを中断**– BizTalk Server がままにするインターチェンジ、バッチ インターチェンジ全体に対して XML ドキュメントを作成するかを指定するには、このオプションを選択します。 このオプションで、インターチェンジ内の 1 つまたは複数のトランザクション セットが失敗した BizTalk Server がその他のすべてのトランザクション セットの処理を継続しながら、トランザクション セットのみを中断します。  
  
       > [!NOTE]
       >  上記 2 つのオプションのいずれか 1 つをオンにした場合、インターチェンジ、グループ、およびトランザクション セット セグメントのプロパティ (BizTalk Server で送信インターチェンジの ISA、GS、ST のヘッダーをどのように作成するかを決定します) は適用されません。 保存されるインターチェンジに含まれているインターチェンジ、グループ、およびトランザクション セットの各ヘッダーは、送信パイプラインがインターチェンジの送信処理を行うときに保持されます。 しかし、アグリーメントでインターチェンジに指定された値を使用する場合、`EDI.PopulateInterchangeValues` コンテクスト プロパティを true に設定します。  
  
2. 保存されたバッチの Visual Studio プロジェクトを次のように作成します。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージ用のスキーマを追加します。  
  
   2. プロジェクトをビルドし、配置します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、保存されたバッチを送信するための送信ポートを次のように作成します。  
  
   1.  送信パイプラインを設定**EdiSend**または**AS2EdiSend**します。  
  
   2.  送信ポートのフィルターをコンテキスト プロパティ `EDI.ReuseEnvelope == True` に設定します。  
  
       > [!NOTE]
       >  このフィルターを設定すると、保存されているすべてのバッチ インターチェンジに送信ポートがサブスクライブされます。 EdiReceive 受信パイプラインは、インターチェンジを保存されたインターチェンジとして識別するために、コンテキスト プロパティ `EDI.ReuseEnvelope` を昇格させます。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)