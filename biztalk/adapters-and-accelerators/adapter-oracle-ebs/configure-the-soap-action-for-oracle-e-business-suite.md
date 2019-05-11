---
title: BizTalk Server での Oracle E-business Suite の SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または Wcf-oracleebs アダプターを使用して、
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca799d96-66e4-4d4e-a632-cb5505e999b4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2e1075960fdb6ca637d81238de776ba30ae0f78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375652"
---
# <a name="configure-the-soap-action-for-oracle-e-business-suite"></a>Oracle E-business Suite の SOAP アクションを構成します。
WCF ベースを使用して Oracle E-business Suite の操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、SOAP アクションを指定する必要があります。 SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。 いずれかから SOAP アクションを指定できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはから、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 ただし、両方の場所からの SOAP アクションを指定する場合、アクションから指定した[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]オーバーライドされます。  
  
 SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。  
  
## <a name="enter-soap-action-from-visual-studio"></a>Visual Studio からの SOAP アクションを入力します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、オーケストレーションの一部として SOAP アクションを指定する必要があります、**式**図形。  
  
1.  BizTalk オーケストレーションで含める、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックス。  
  
2.  ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。  
  
3.  BizTalk 式エディタで、アクションを指定します。 以下に例を示します。  
  
    ```  
    OutboundMessage(WCF.Action)="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY"  
    ```  
  
     詳細については、**式**図形と BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a>BizTalk Server 管理からの SOAP アクションを入力します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として SOAP アクションを指定する必要があります。  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a>WCF カスタム ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
5. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (GL_ALLOC_HISTORY テーブルにレコードを挿入) するための Op1 と Op2 (GL_ALLOC_HISTORY テーブル内のレコードを更新) するメッセージを受信する 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
         <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
       </BtsActionMapping>  
       ```  
  
        アクション マッピングのアプローチは、アクションのセットを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属しているメッセージの有効化の観点からの柔軟性を提供します。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)します。
  
#### <a name="enter-a-soap-action-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポートの SOAP アクションを入力します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4. ポートのプロパティ ダイアログ ボックスから、**型**一覧から、以前では、追加し、をクリックし、選択、Wcf-oracleebs アダプター**構成**します。  
  
5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。  
  
6. **アクション**テキスト ボックスで、操作の SOAP アクションを指定します。 次の方法では、アクションを指定できます。  
  
   -   **シングル アクション形式を使用して**します。 Wcf-oracleebs、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。 以下に例を示します。  
  
       ```  
       InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
       ```  
  
   -   **アクション マッピング形式を使用して**します。 1 つの Wcf-oracleebs ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。 たとえば、送受信 (GL_ALLOC_HISTORY テーブルにレコードを挿入) するための Op1 と Op2 (GL_ALLOC_HISTORY テーブル内のレコードを更新) するメッセージを受信する 1 つの Wcf-oracleebs ポート、SOAP アクションは次のように指定できます。  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
         <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
       </BtsActionMapping>  
       ```  
  
        アクション マッピングのアプローチは、アクションのセットを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属しているメッセージの有効化の観点からの柔軟性を提供します。  
  
        SOAP アクションの形式は操作ごとに異なります。 各操作のアクションの形式の詳細については、次を参照してください。[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)します。
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)