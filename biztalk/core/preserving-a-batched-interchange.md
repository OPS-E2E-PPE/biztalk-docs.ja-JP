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
ms.openlocfilehash: 4360e4e042ee7302935d20029be2880aee9f4be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271163"
---
# <a name="preserving-a-batched-interchange"></a>バッチ インターチェンジの保存
このトピックでは、インターチェンジのトランザクション セットを分割せず 1 つのドキュメントとしてバッチ EDI インターチェンジを処理するアグリーメントを構成する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-receiving-and-sending-of-a-preserved-batch"></a>受信および保存されたバッチの送信を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。 **パーティとビジネス プロファイル** ページで、受信したバッチ インターチェンジを解決するアグリーメントのパーティをクリックします。 **契約**セクション、ページのアグリーメントを右クリックし、をクリックして**プロパティ**します。 **アグリーメントのプロパティ**ダイアログ ボックスの一方向アグリーメント タブ (受信のバッチ インターチェンジが解決先) で、次の操作を行います。  
  
   1.  **識別子** ページで、ISA5、ISA6、ISA7、および ISA8 の値を入力の値を入力します。 受信バッチ処理インターチェンジがこのアグリーメントに解決できるように、適切な値を入力してください。  
  
   2.  **ローカル ホスト設定**ページ (**インターチェンジの設定**) 下で、**受信者の設定**セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。  
  
       -   **インターチェンジの保存 - エラーでインターチェンジを中断**– BizTalk Server がままにするインターチェンジ、バッチ インターチェンジ全体に対して XML ドキュメントを作成するかを指定するには、このオプションを選択します。 このオプションで、インターチェンジ内の 1 つまたは複数のトランザクション セットが失敗した BizTalk Server がそのインターチェンジ全体を中断します。  
  
       -   **インターチェンジの保存 - エラーのトランザクション セットを中断**– BizTalk Server がままにするインターチェンジ、バッチ インターチェンジ全体に対して XML ドキュメントを作成するかを指定するには、このオプションを選択します。 このオプションで、インターチェンジ内の 1 つまたは複数のトランザクション セットが失敗した BizTalk Server がその他のすべてのトランザクション セットの処理を継続しながら、トランザクション セットのみを中断します。  
  
       > [!NOTE]
       >  上記で説明した 2 つのオプションのいずれかを選択した場合、インターチェンジ、グループ、およびトランザクション セット セグメント プロパティ (BizTalk Server が送信インターチェンジの ISA、GS、および ST ヘッダーを作成する方法を決定) は適用されません。 送信パイプラインが送信を処理するときに、インターチェンジ、グループ、およびトランザクション セットのヘッダーが保存されているインターチェンジ内に存在するが保持されます。 ただし、インターチェンジのアグリーメントで指定された値を使用して行う場合は、設定、`EDI.PopulateInterchangeValues`コンテキスト プロパティを true にします。  
  
2. 次のように保存されたバッチ用の Visual Studio プロジェクトを作成します。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージのスキーマを追加します。  
  
   2. プロジェクトをビルドし、配置します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のように保存されたバッチを送信する送信ポートを作成します。  
  
   1.  送信パイプラインを設定**EdiSend**または**AS2EdiSend**します。  
  
   2.  送信ポートのフィルター コンテキスト プロパティに設定`EDI.ReuseEnvelope == True`します。  
  
       > [!NOTE]
       >  送信ポートが保存されるすべてのバッチ インターチェンジにサブスクライブすることにより、このフィルターを設定します。 EdiReceive 受信パイプラインは、コンテキスト プロパティを昇格`EDI.ReuseEnvelope`としては、インターチェンジを識別します。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)