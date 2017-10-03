---
title: "Oracle E-business Suite のバインド プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddb414ae80e7cff6717d232d1734ec8b98cd2006
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a>Oracle E-business Suite のバインド プロパティを構成します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。 このセクションで説明からのバインドのプロパティを設定する方法について[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマを生成するときに、バインドのプロパティを指定する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一部としてのバインドのプロパティを指定または Oracle E-business Suite からメッセージを送受信するためのポートを受信する必要があります。  
  
 バインドのプロパティについては、バインドのプロパティの一覧を含め、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
## <a name="specifying-binding-properties-from-visual-studio"></a>Visual Studio からバインドのプロパティを指定します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用してバインド プロパティを指定するには  
  
1.  BizTalk プロジェクトを右クリックし **生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**、順にクリック**を構成します。**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインディング プロパティを指定します。  
  
6.  **[OK]**をクリックします。  
  
#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインド プロパティを指定するには  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]**をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] **Wcf-oracleebs**です。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成された Wcf-oracleebs ポートがある場合は、ポートの一覧から、ポートを選択します。  
  
5.  **[次へ]**をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、クリックして**構成**.  
  
7.  をクリックして、**バインド プロパティ**タブをクリックし、バインディングの値を指定、存在する場合、スキーマを生成する前に必要とします。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の選択した場合は、Wcf-oracleebs 送信ポートをバインドのプロパティを指定する必要があります。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合は、バインドのプロパティの新しい値は、メタデータの生成中のデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
8.  **[OK]**をクリックします。  
  
## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからバインドのプロパティを指定します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部としてのバインドのプロパティを指定する必要があります。  
  
#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインド プロパティを指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
5.  **バインディングの種類**一覧で、 **oracleEBSBinding**です。  
  
6.  **構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。  
  
#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポートのバインド プロパティを指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-oracleebs アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。  
  
    > [!NOTE]
    >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)