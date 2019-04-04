---
title: Oracle E-business Suite のバインド プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1e2d60ede3e41c08b15d3839f6ece41a68aa373
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989179"
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a>Oracle E-business Suite のバインド プロパティを構成します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。 このセクションでは、バインドのプロパティを設定する方法についての情報を提供します。[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマの生成中にバインディング プロパティを指定する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一環としてのバインドのプロパティを指定するか、受信ポートを送信または Oracle E-business Suite からメッセージを受信する必要があります。  

 バインドのプロパティについては、バインドのプロパティの一覧を含む、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

## <a name="specifying-binding-properties-from-visual-studio"></a>Visual Studio からバインドのプロパティを指定します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用してバインドのプロパティを指定するには  

1.  BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**、順にクリックします**構成**.  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインド プロパティを指定します。  

6.  **[OK]** をクリックします。  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインドのプロパティを指定するには  

1. BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 **Wcf-oracleebs**します。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成された Wcf-oracleebs ポート既にある場合は、ポートの一覧から、ポートを選択します。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、順にクリックします**構成**.  

7. をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。 バインド プロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。  

   > [!NOTE]
   >  既存を選択した場合は、Wcf-oracleebs 送信ポート、バインディングのプロパティを指定する必要があります。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合は、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

8. **[OK]** をクリックします。  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからバインドのプロパティを指定します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部としてのバインドのプロパティを指定する必要があります。  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

5. **バインドの種類**一覧で、 **oracleEBSBinding**します。  

6. **構成**ボックスに、さまざまなバインドのプロパティの値を指定してクリックして**OK**。  

#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポートのバインドのプロパティを指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)を参照してください。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した Wcf-oracleebs アダプターを選択してをクリックして**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。  

   > [!NOTE]
   >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  

## <a name="see-also"></a>参照  
 [Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)