---
title: パーティの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.party
helpviewer_keywords:
- Administration Console [BizTalk Server], parties
- managing [parties]
- managing [parties], about managing parties
- parties, managing
ms.assetid: 96d2bcb3-1e38-4dad-a0d6-e5913ba531e7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f639ad516ec4f4a61406b9690d2d52f2ea98599f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009651"
---
# <a name="managing-parties"></a>パーティの管理
使用して、**パーティ** ノードを設定できます (パーティ) のビジネス パートナーまたは社内の部署 (ビジネス プロファイル) を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションが連携します。 詳細については、次を参照してください。[取引パートナー](../core/trading-partners-and-business-profiles.md)です。  

パーティは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して作成および構成できます。 BizTalk Server にパーティを作成してから、オーケストレーションを使用して、パーティと連携する場合があります。 パーティは、ロールを通じてオーケストレーションと連携します。 たとえば、オーケストレーションに出荷ロールがあるとします。 出荷業者には、1 つ以上のパーティが関連付けられます。 オーケストレーションで最も低コストの商品の出荷業者を決定する際に、出荷業者ロールのパーティの価格を比較できます。  
  
 パーティを参加させて、特定のロールに関連付ける必要があります。 パーティを参加させることで、オーケストレーションとパーティを連携させることができます。 参照してください[参加させる、またはロールに対してパーティを参加解除方法](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)です。
 
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="create-or-edit-a-party"></a>パーティを作成または更新
  
1.  開いている**BizTalk Server 管理**です。  展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を BizTalk グループを展開しを右クリックして**パーティ****新規**、し、**パーティ**です。  
  
2.  **全般** ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|パーティ名を入力します。|  
    |**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理します。**|パーティが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をホストしている同じ取引先を表すように指定する場合は、このチェック ボックスをオンにします。 **重要:** に付属する既定のパイプラインを使用するソリューション 2 パーティ TPM の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、少なくとも 1 つのパーティの場合は、このチェック ボックスを選択する必要があります。 **注:** このチェック ボックスをオフにすると、一部のプロパティは、このパーティのアグリーメントの作成中に無効になります。|  
    |**追加のプロパティ – 名前/値**|パーティに関する任意の情報を格納する、名前と値の組み合わせを入力します。 名前と値の組み合わせは、必要な数だけ追加できます。 **注**: どのような処理の名前と値のペアが、BizTalk Server によって使用されません。 このデータは、情報提供のみを目的のはします。|  
    |**Del**|選択すると、選択した名前と値のペアを削除します。|  
  
3.  **送信ポート** ページで、次の操作を行います。  
  
    > [!NOTE]
    >  BizTalk Server では、送信ポートの関連付けはアグリーメント レベルで行われます。 **送信ポート**下位互換性は、パーティのプロパティの一部として使用可能なページです。 送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。 ただし、その逆は真ではありません。 送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**送信ポートの名前**|ドロップダウン リストから、このパーティにバインドする送信ポートを選択します。|  
    |**送信ポートの URI**|送信ポートのアドレスを表示します。|  
    |**[削除]**|選択した送信ポートをパーティから削除するを選択します。|  
    |**プロパティ**|選択すると表示、**送信ポートのプロパティ**選択した送信ポートのダイアログ ボックス。|  
  
4.  **証明書** ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**参照**|表示するを選択して、**証明書の選択**ダイアログ ボックスで、パーティに送信されるメッセージに適用するローカル コンピューターまたはその他のユーザーの証明書ストアから署名証明書を選択します。|  
    |**共通名**|選択した証明書の説明を表示します。|  
    |**拇印**|パーティの解決および署名の確認に使用される秘密キー証明書の拇印を表示します。 証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。|  
    |**証明書を削除します。**|表示されている証明書の削除を選択します。|  
  
5.  選択**適用**、プロパティを受け入れるかを選択する**OK**構成設定を完了します。 どちらの操作を行った場合も、設定が有効になります。  

### <a name="update-an-existing-party"></a>既存のパーティを更新します。
パーティをロールに参加させ、ポートをバインドした後、次の操作を行うことができます。  
  
-   パーティの名前と説明を編集します。  
-   パーティの証明書を編集します。  
-   パーティがホストする組織かどうかを指定します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]

1. **BizTalk Server 管理コンソール**を選択して**パーティ**です。

2. **パーティとビジネス プロファイル**ウィンドウ、表示または編集するパーティを右クリックして、選択**プロパティ**です。  

3. 表示またはプロパティを編集します。 

4. 選択**適用**、プロパティを受け入れるかを選択する**OK**構成設定を完了します。 どちらの操作は、設定を検証します。  

## <a name="delete-a-party"></a>パーティを削除する
使用してパーティを削除、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!IMPORTANT]
>  ロールに参加しているパーティは削除できません。 パーティを削除する前に、そのパーティが参加しているすべてのロールから参加を解除する必要があります。 参照してください[参加させる、またはロールに対してパーティを参加解除方法](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)です。 

1. **BizTalk Server 管理コンソール****パーティ**を削除し、選択するパーティを右クリックして**削除**です。  
  
2.  **パーティ削除の確認**ダイアログ ボックスで、**はい**パーティを削除します。  

## <a name="search-for-a-party"></a>パーティの検索
使用することができます、多数のパーティを作成した場合、**検索**オプションを表示するパーティを表示します。  

1. **BizTalk Server 管理コンソール****パーティ**です。

3.  **パーティとビジネス プロファイル**ペインの右上隅の上に検索文字列を入力してください、**検索パーティ**テキスト ボックス、および検索アイコンを選択します。 Enter キーを押して検索を開始することもできます。  
  
     検索時には次の点を考慮してください。  
  
    -   検索文字列と小文字は区別されません。
  
    -   名前 (サブ文字列の検索) 内のテキストを検索することができます。 たとえば、'ar' を検索した場合は、検索文字列で始まるパーティ (Artist など) または名前に検索文字列が含まれているパーティ (Party1 など) が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールに表示されます。  
  
    -   検索操作は、パーティ名に制限されます。  
  
4.  検索結果をクリアするには、検索テキスト ボックスの横にある赤い 'x' を選択します。  
  
## <a name="see-also"></a>参照  
 [ロール リンクの管理](../core/managing-role-links.md)   
 [パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
 [EDI および AS2 ソリューションの管理](../core/managing-edi-and-as2-solutions.md)