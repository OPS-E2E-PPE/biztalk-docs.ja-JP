---
title: バッチ インターチェンジの分割 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67bef19-77fb-47a9-88f3-ee20043b3691
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1cb3c6c912985a81a2265afa11bebc636381c5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024064"
---
# <a name="splitting-a-batched-interchange"></a>バッチ インターチェンジの分割
このトピックでは、バッチ EDI インターチェンジのトランザクション セットを分割して、インターチェンジを処理するアグリーメントを構成する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-receive-a-split-edi-interchange"></a>分割された EDI インターチェンジを受信するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード。 **パーティとビジネス プロファイル** ページで、受信したバッチ インターチェンジを解決するアグリーメントのパーティをクリックします。 **契約**セクション、ページのアグリーメントを右クリックし、をクリックして**プロパティ**します。 **アグリーメントのプロパティ**ダイアログ ボックスの一方向アグリーメント タブ (受信のバッチ インターチェンジが解決先) で、次の操作を行います。  
  
   1.  **識別子** ページを受信したバッチ インターチェンジがこのアグリーメントに解決できるように、適切な値を入力するかどうかを確認します。  
  
       -   場合に**X12**: 設定の ISA5、ISA6、ISA7、ISA8、します。  
  
       -   場合に**Edifact**: 設定 UNB2.1、UNB2.2、UNB3.1、および [unb3.2]。  
  
   2.  **ローカル ホスト設定**ページ (**インターチェンジの設定**) 下で、**受信者の設定**セクションの**受信バッチ処理オプション**、1 つに、次のオプションを選択します。  
  
       -   **トランザクション セットとして分割されたインターチェンジがエラーのトランザクション セットを中断**– BizTalk Server がインターチェンジを個別の XML ドキュメントの各トランザクション セットを解析する必要がありますを指定するには、このオプションを選択します。 こうすることによって、適切なエンベロープがトランザクション セットに適用され、トランザクション セット ドキュメントがメッセージ ボックスにルーティングされるようになります。 このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server はこれらのトランザクション セットだけを中断します。  
  
       -   **トランザクション セットとして分割されたインターチェンジがエラーでインターチェンジを中断**– BizTalk Server がインターチェンジを個別の XML ドキュメントの各トランザクション セットを解析する必要がありますを指定するには、このオプションを選択します。 こうすることによって、適切なエンベロープがトランザクション セットに適用され、トランザクション セット ドキュメントがメッセージ ボックスにルーティングされるようになります。 このオプションを使用すると、インターチェンジ内の 1 つまたは複数のトランザクション セットが検証に失敗した場合に、BizTalk Server がインターチェンジ全体を保留するようになります。  
  
2. 保存されたバッチの Visual Studio プロジェクトを次のように作成します。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成し、バッチ内のすべてのメッセージ用のスキーマを追加します。  
  
   2. プロジェクトをビルドし、配置します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、分割されたバッチを送信するための送信ポートを次のように作成します。  
  
   1.  送信パイプラインを設定**EdiSend**または**AS2EdiSend**します。  
  
   2.  送信ポートのフィルターを、各トランザクション セットを取得するのに必要な値に設定します。たとえば、BTS.MessageType に設定します。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)