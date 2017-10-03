---
title: "EDI AS2 ソリューションのバインドをインポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b918fa2-44f2-4f57-95af-36858cea0d86
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba7e0c601276779067c1699da1526491dc3f7ca2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-bindings-for-an-edi-as2-solution"></a>EDI AS2 ソリューションのバインドをインポートする方法
このトピックでは、EDI または AS2 ソリューションの構成を別のコンピューターにインポートする方法について説明します。 EDI/AS2 ソリューションの展開は、BizTalk アプリケーションの展開に統合されています。 この機能は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールおよび BTSTask コマンド ライン ツールから利用できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成をインポートするには、インポート元のコンピューターで該当するバインドをエクスポートすることによって作成したバインド ファイルを使用します。 バインド ファイルに構成をエクスポートする方法の詳細については、次を参照してください。 [EDI AS2 ソリューションのバインドをエクスポートする方法](../core/how-to-export-bindings-for-an-edi-as2-solution.md)です。 構成から作成されたバインド ファイルについては、次を参照してください。[バインド ファイルの構造体](../core/structure-of-a-binding-file.md)です。  
  
 また、.msi ファイル使用して、アプリケーションのインポート時にバインドをインポートすることもできます。 詳細については、次を参照してください。、[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 BTSTask コマンドを使用して、バインドをエクスポートおよびインポートすることもできます。 BTSTask の詳細については、次を参照してください。、 [BTSTask コマンドライン リファレンス](../core/btstask-command-line-reference.md)でトピック[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループのメンバーとしてログオンする必要があります。 詳細については、次を参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
-   参照を追加する必要があります、 **BizTalk EDI アプリケーション**EDI アプリケーションとして使用される BizTalk アプリケーションからです。 BizTalk EDI アプリケーションへの参照を追加する方法の詳細については、次を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。  
  
## <a name="importing-bindings"></a>バインドのインポート  
 構成をインポートすると、既存の EDI プロパティが上書きされます。 既存のパーティと同じ名前のパーティのプロパティをインポートすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、既存のパーティの EDI プロパティ (つまり、すべてのバインド) が上書きされます。 また、EDI グローバル プロパティをインポートすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、既存の EDI グローバル プロパティが上書きされます。  
  
 構成をインポートした後で、パスワードを再構成する必要があります。 セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EDIFACT プロパティから UNB6.1 および UNB6.2 フィールドが削除され、X12 プロパティから ISA1、ISA2、ISA3、および ISA4 フィールドが削除されます。 バインドをインポートした後、EDI メッセージを処理する前に、これらの機密性の高いフィールドを再構成する必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でバインドのインポートに失敗した場合は、バインド ファイルの Host Trusted プロパティが、ホストの "信頼されている認証" プロパティと異なる可能性があります。 この問題は、バインド ファイルで Host Trusted プロパティを変更することによって解決できます。  
  
> [!NOTE]
>  BizTalk Server の以前のリリースから [!INCLUDE[prague](../includes/prague-md.md)] へのバインド ファイルのインポートは失敗する場合があります。 [!INCLUDE[prague](../includes/prague-md.md)] の取引先管理モデルが大幅に変わったため、以前のバージョンの BizTalk Server からバインド ファイルをインポートすると、新しいモデルに従って [!INCLUDE[prague](../includes/prague-md.md)] にエンティティが作成されない可能性があります。 詳細については、次を参照してください。[新しい TPM エンティティにパーティ定義前 BizTalk Server のバージョンの変換での操作方法?](../core/how-to-import-bindings-for-an-edi-as2-solution.md#BKMK_Party)です。  
  
### <a name="to-import-the-configuration-from-a-binding-file"></a>バインド ファイルから構成をインポートするには  
  
1.  構成のインポート先となるコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。  
  
2.  EDI および AS2 構成のインポート をポイントする BizTalk アプリケーションを右クリックして**インポート**、クリックして**バインド**です。  
  
3.  バインドのインポート ダイアログ ボックスで、バインド ファイルを格納している場所に移動し、をクリックして**開く**です。  
  
4.  バインドをインポートした後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。 手動で、すべての EDI パスワード フィールドを適切な値に設定します。  
  
##  <a name="BKMK_Party"></a>新しい TPM エンティティにパーティ定義で以前 BizTalk Server のバージョンに変換する方法は?  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、パーティ定義は基本的に、2 つの取引先間でメッセージが交換される方法を定義するアグリーメントです。 [!INCLUDE[prague](../includes/prague-md.md)] では、EDI および AS2 メッセージについて多くの変更が行われており、新しい取引先管理 (TPM) モデルでは、2 つの取引ビジネス プロファイル間にアグリーメントを作成する必要があります。 そのため、基本的に、アグリーメントが存在するためには、最初に 2 つの取引先、両方の取引先のプロファイル、および両方の取引ビジネス プロファイルのプロトコル設定を定義する必要があります。 これらのエンティティを定義したら、取引先アグリーメントを作成できます。  
  
> [!NOTE]
>  TPM の機能強化に関連する詳細[!INCLUDE[prague](../includes/prague-md.md)]を参照してください[取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)です。  
  
 新しい TPM オブジェクト モデルということは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] で作成した EDI アプリケーションを [!INCLUDE[prague](../includes/prague-md.md)] に移行できないと思われますが、 答えはノーです。 BizTalk Server 2006 R2 または BizTalk Server 2009 から既存のアプリケーションを再利用できる[!INCLUDE[prague](../includes/prague-md.md)]を使用して、パーティ移行ツールを以前のバージョンの BizTalk Server からパーティ データを移行します。 ツールの詳細については、次を参照してください。 [EDI アイテムを BizTalk Server の以前のバージョンから移行する](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)です。  
  
## <a name="see-also"></a>参照  
 [バインドのインポート](../core/importing-bindings2.md)