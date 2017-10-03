---
title: "EDI AS2 ソリューションのバインドをエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 856ab630-66c4-4496-884a-fdbe641143c5
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aceeb81933324d5b3c164396290fe7b99cdc7295
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-for-an-edi-as2-solution"></a>EDI AS2 ソリューションのバインドをエクスポートする方法
このトピックでは、EDI または AS2 ソリューションとして設定されたコンピュータから構成をエクスポートする方法について説明します。 これにより、自動化された方法で別のコンピュータと同じ構成を設定できるようになります。 バインドのエクスポート元としては、アプリケーション、グループ、アセンブリがあります。  
  
 バインド ファイルを作成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用します。 .xml バインド ファイルには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成に関するすべての情報が含まれています。 このファイルには、特定のセキュリティ情報を除くすべての EDI および AS2 の構成プロパティが含まれています。 バインド ファイル (などの EDI および AS2 ノード) 内のノードの詳細については、次を参照してください。[バインド ファイルの構造体](../core/structure-of-a-binding-file.md)です。 EDI/AS2 バインドに関する一般的な情報については、以下の「[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バインド ファイルの EDI および AS2 ノード」を参照してください。  
  
 また、.msi ファイル使用して、アプリケーションのエクスポート時にバインドをエクスポートすることもできます。 詳細については、次を参照してください。、[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。 BTSTask コマンドを使用して、バインドをエクスポートおよびインポートすることもできます。 BTSTask の詳細については、次を参照してください。 [BTSTask コマンドライン リファレンス](../core/btstask-command-line-reference.md)です。  
  
 **バインドをエクスポートします。**  
  
 構成をエクスポートすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって、バインドされているすべてのパーティの EDI プロパティおよびその他のパーティ情報が自動的にエクスポートされます。 グローバル パーティ情報のエクスポートをアクティブ化すると、オーケストレーションにバインドされていないパーティのプロパティおよびグローバル EDI プロパティも [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエクスポートされます。 グローバル パーティ情報は、次の 3 つの方法でエクスポートできます。  
  
-   [バインドのエクスポート] ダイアログ ボックスで "グローバル パーティ情報をエクスポートする" プロパティをオンにする。  
  
-   MSI ファイルのエクスポート ウィザードの [リソースの選択] ペインで [グローバル パーティ] をオンにする。  
  
-   次の手順に従って BTSTask コマンド ライン ツールで GlobalParties スイッチを使用する。  
  
    ```  
    BTSTask ExportBindings -Destination:value ((([-ApplicationName:value] | [-AssemblyName:value]) [-GlobalParties]) | [-GroupLevel])  
    ```  
  
 セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EDIFACT プロパティから UNB6.1 および UNB6.2 フィールドが削除され、X12 プロパティから ISA1、ISA2、ISA3、および ISA4 フィールドが削除されます。  
  
 バインドのエクスポート、アプリケーションのエクスポート、および BTSTask コマンド以外にも、手動で XML バインド ファイルを作成することもできます。 これにより、基幹業務アプリケーションからパーティおよび EDI 設定をエクスポートできます。 バインドのインポート コマンドまたは BTSTask コマンドを使用して、バインドをインポートすることも可能になります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループのメンバーとしてログオンする必要があります。 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマニュアルの「BizTalk アプリケーションの展開と管理に必要なアクセス許可」を参照してください。  
  
### <a name="exporting-the-configuration-into-a-binding-file"></a>バインド ファイルへの構成のエクスポート  
  
1.  構成のエクスポート元となるコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。  
  
2.  構成のコピー元 をポイントする BizTalk アプリケーションを右クリックして**エクスポート**、クリックして**バインド**です。  
  
    > [!NOTE]
    >  BTSTask ユーティリティを使用して、構成をエクスポートおよびインポートすることもできます。  
  
3.  エクスポート オプションを選択して、現在のアプリケーションまたはグループからバインドをエクスポートするか、またはアセンブリのバインドをエクスポートします。  
  
4.  すべてのパーティをエクスポートするし、非依存プロパティには、オーケストレーションがバインドされていない場合でもクリックして**グローバル パーティ情報をエクスポート**です。  
  
    > [!NOTE]
    >  クリックしない場合**グローバル パーティ情報をエクスポート**、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルに、オーケストレーションにバインドされているパーティのプロパティがエクスポートされます。 ただしはエクスポートされません、オーケストレーションにバインドされていないパーティをクリックした場合を除き、**グローバル パーティ情報をエクスポート**です。  
  
    > [!NOTE]
    >  バインド ファイルを生成中に、**グローバル パーティ情報をエクスポート**プロパティが選択されているコンピューターで定義されたすべてのパーティの構成が含まれます。 コンピュータで定義されたパーティの完全なセットのサブセットの構成は、エクスポートできません。  
  
5.  をクリックして**OK**バインドをエクスポートします。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パスワード、セキュリティ情報、認証情報などの EDI の機密フィールドはエクスポートされません。 ただし、EDI の機密フィールドの空白文字列はエクスポートされます。 バインドを別のコンピュータにインポートしたら、EDI の機密フィールドの値を手動で設定する必要があります。  
  
6.  バインドをインポートするコンピュータを後から設定するために、パスワード、セキュリティ情報、認証情報などの EDI の機密フィールドをメモなどに記録しておきます。  
  
## <a name="edi-and-as2-nodes-in-the-biztalk-server-binding-file"></a>BizTalk Server バインド ファイルの EDI および AS2 ノード  
 構成をエクスポートする場合、**グローバル パーティ情報をエクスポート**プロパティを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルを次のノードが生成されます。  
  
```  
EdiData  
   PartyEDIProperties  
      PartnerAgreement  
         Contacts  
      PartnerEdifact  
         PartnerEdifactReceiverGroups  
         PartnerEdifactSenderGroups  
      PartnerAckValidation  
      PartnerX12  
      PartnerX12ReceiverGroups  
      PartnerX12SenderGroups  
      PartnerBatchUpdatable  
      PartnerAS2CommonUpdatable  
      PartnerAS2  
```  
  
 EDI グローバル プロパティは、次のノードのバインド ファイルに追加されます。  
  
```  
EDIGlobalProperties  
   EDIGlobalProperties  
      GlobalCommon  
      GlobalEdiFact  
      GlobalX12  
```  
  
 EDI および AS2 ノードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バインド ファイルの末尾に追加されます。 EdiData ノードは、Party Collection ノードの下の Party サブノードに追加され、EdiGlobalProperties ノードは、Party Collection ノードの後に同じレベルで追加されます。 BizTalk バインド ファイル内の EDI および AS2 ノードに関する詳細については、次を参照してください。[バインド ファイルの構造体](../core/structure-of-a-binding-file.md)です。  
  
 EdiData ノードは省略可能です。 ただし、EdiData ノードが存在する場合、EdiData の下のサブノードも存在する必要があります。 同様に、EdiGlobalProperties ノードも省略可能ですが、EdiGlobalProperties ノードが存在する場合は、このノードの下のサブノードも存在する必要があります。  
  
 EDI および AS2 バインド ファイル ノードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのパートナー アグリーメント マネージャーのプロパティ ページに直接は対応していません。 一部の EDI および AS2 バインド ファイル ノードには、sender ロールで使用されるプロパティと receiver ロールで使用されるプロパティが含まれています。 ロールは、ノードの IsSender プロパティによって指定されます。 sender ロールおよび receiver ロールで使用されないノード (PartnerAgreement、PartnerBatchUpdatable、PartnerAS2Updatable、および GlobalCommon) では、IsSender は常に False です。  
  
 PartnerEdifact ノードおよび PartnerX12 ノードには、IsSender が True または False のいずれに設定されている場合でも、receiver ロールと sender ロールが含まれます。 たとえば、IsSender が True に設定されている場合でも、PartnerEdifact には Una1 フィールド (インターチェンジ受信者としてのパーティで使用される) が含まれます。 また、IsSender が False に設定されている場合でも、PartnerEdifact には Unb5CheckDup フィールド (インターチェンジ送信者としてのパーティで使用される) が含まれます。 ただし、IsSender が True に設定されている場合は、インターチェンジ受信者としてのパーティのフィールドは UI またはエンジンで使用されず、デフォルト値が指定されます。 同様に、IsSender が False に設定されている場合は、インターチェンジ送信者としてのパーティのフィールドは UI またはエンジンで使用されず、デフォルト値が指定されます。  
  
 プロパティのデフォルトが Null の場合、フィールドで値が指定されていない限り、フィールドはバインド ファイルに含まれません。  
  
 バインド ファイルのデータは、BizTalk 管理データベース (BizTalkMgmtDb) のテーブルに格納されます。