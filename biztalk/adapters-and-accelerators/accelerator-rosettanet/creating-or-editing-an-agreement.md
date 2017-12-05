---
title: "作成または編集アグリーメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- agreements, about agreements
- agreements, modifying
- agreements, creating
- agreements
- trading partners, agreements
- creating, agreements
- modifying, agreements
- agreements, trading partners
ms.assetid: 4bbe4b57-d6ec-4448-9c80-2aecd98e0dc7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ea033770504b0e0024a831e0ad8d8727603046e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-or-editing-an-agreement"></a>作成するか、契約の編集
ここでは、取引先アグリーメント (TPA) の作成方法または編集方法について説明します。 取引先アグリーメントは、2 つの取引先の間に、ID、PIP (Partner Interface Process)、アクション URL、シグナル URL、同期 URL、関連付けられたプロトコルなどのリレーションシップを構成します。  
  
 取引先アグリーメントには、プロセス構成、ホーム組織、パートナー、およびアグリーメントに関する設定が含まれています。 アグリーメントには、これらすべての設定が必要になります。 プロセス構成は RosettaNet PIP またはカスタム スキーマのいずれに基づいて作成できますが、その場合は構成を作成する必要があります。 また、ホーム組織と取引先組織の両方を定義する必要があります。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]不明なパーティ間のメッセージ交換をサポートしていません。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、これらすべての設定に基づいて、メッセージを処理および検証します。 たとえば CIDX メッセージの場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は RosettaNet Implementation Framework (RNIF) のバージョン (1.1 のみ)、[0A1 アグリーメント] (非 0A1 のみ)、および `Is Single Action` プロパティ (シングル アクションのみ) に基づいて検証を行います。 CIDX メッセージは、RNIF のバージョン「1.1」、"0A1"に、0A1 アグリーメントを設定する場合にのみを検証し、`Is Single Action`プロパティを`True`です。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]また、アグリーメントのプロパティにプロセス構成プロファイルの設定と整合性があることを検証します。 たとえば、プロファイルの `Standard` プロパティが CIDX に設定されているかどうか、およびアグリーメントの [0A1 アグリーメント] プロパティが非 0A1 に設定されているかどうかが確認されます。  
  
 プロセスがアクティブな状態でアグリーメントを変更すると、予測不可能な結果が生じることがあります。 クリックするとすぐに、アグリーメントのプロパティへの変更が適用されます**適用**または**OK**を受け入れるには予測できませんプロセスのどのステージが実行されています。 アグリーメントを変更した後は、現在のプロセスの新しいアクティビティや新しいプロセスはすべて、変更されたアグリーメント プロパティを使用します。 ただし、アグリーメントを変更するときに実行中であったプロセスは、処理中のメッセージには以前のアグリーメント プロパティを既に使用していた可能性があります。  
  
 アグリーメントを作成したら、アクティブ化して、そのアグリーメントに関連付けられたメッセージを送信または受信できるようにする必要があります。 アグリーメントに関連付けられたメッセージが送信または受信されないように、アグリーメントを非アクティブ化することもできます。 アグリーメントを編集するには、非アクティブ化して、編集後に再度アクティブ化します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、この情報を BTARNCONFIG データベースの TPAConfig テーブルに保存します。  
  
 次の表に、取引先アグリーメントの設定をタブごとに整理して示します。既定では、最も一般的に使用される値が設定されています。 これらの設定を作成して編集するための手順は、表の後に記載されています。  
  
|タブ|設定|使用方法|  
|---------|-------------|-----------|  
|**全般**|**名前**|Fabrikam_To_Contoso_3A2 など、アグリーメントの一意の名前。<br /><br /> 必須フィールド。|  
|**全般**|**プロセスの構成**|PIP の識別子。<br /><br /> この番号によって、このアグリーメントに関連付けられたプロセス構成が識別されます。<br /><br /> 既定値は、プロセス構成一覧の最初に表示される値です。 ドロップダウン リストには、以前入力されたすべてのプロセス構成が含まれます。<br /><br /> 必須フィールド。|  
|**全般**|**自分の所属組織**|ドロップダウン リストから選択されたホーム組織。<br /><br /> 必須フィールド。|  
|**全般**|**パートナー組織**|ドロップダウン リストから選択された取引先組織。<br /><br /> 必須フィールド。|  
|**全般**|**Description**|取引先アグリーメントの説明。|  
|**全般**|**RNIF のバージョン**|[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がアグリーメントの通信に使用する RNIF のバージョン。<br /><br /> 指定できます**V01.10.00**または**[v02.00.01]** (既定)。<br /><br /> 必要があります**V01.10.00** CIDX 用です。|  
|**全般**|**ホーム ロール**|ホーム組織のロール。<br /><br /> 開始側ロールまたは応答側ロールを指定できます。|  
|**全般**|**0A1 アグリーメント**|エラーが発生した場合に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がエラー通知メッセージ (0A1 PIP) を返すかどうかを示します。<br /><br /> 指定できます**非 0A1** (既定) または**0A1**です。<br /><br /> 必要があります**非 0A1** CIDX 用です。|  
|**全般**|**使用方法**|アグリーメントが使用するシナリオの種類を示します。<br /><br /> 指定できます**テスト**(既定) または**運用**です。|  
|**全般**<br /><br /> (**アプリケーション アダプター**領域)|**アセンブリ名**|ファイル システムから選択できる ApplicationAdapter のファイル名。<br /><br /> 既定値は空の文字列です。|  
|**全般**<br /><br /> (**アプリケーション アダプター領域**)|**クラス名**|[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が使用する ApplicationAdapter のクラス名。<br /><br /> 既定値は\<none\>です。|  
|**全般**<br /><br /> (**検証アダプター領域**)|**アセンブリ名**|ファイル システムから選択できる ValidationAdapter のファイル名。 既定値は空の文字列です。|  
|**全般**<br /><br /> (**検証アダプター領域**)|**クラス名**|[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が使用する ValidationAdapter のクラス名。<br /><br /> 既定値は\<none\>です。|  
|**ポート**|**アクションの URL**|ホーム組織がアクション メッセージを送信する先の URL。 たとえば、http://FabrikamServer/BTARNApp/RNIFReceive.aspx。<br /><br /> このフィールドは、次の項目がすべて該当する場合に必須です。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`True`します。<br /><br /> -**ホーム ロール**アグリーメントの設定が**イニシエーター**です。<br /><br /> これは、も必要なフィールドは、次に該当する場合 (この場合は、**シグナル URL**フィールドも必須です)。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`False`します。<br /><br /> このフィールドは、"http://domain"または"https://domain"のいずれかで始まる 1-有効な URI を入力する必要があります。|  
|**ポート**|**シグナル URL**|ホーム組織がシグナル メッセージを送信する先の URL。 たとえば、http://FabrikamServer/BTARNApp/RNIFReceive.aspx。<br /><br /> このフィールドは、次の項目が該当する場合に必須です。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`True`します。<br /><br /> -**ホーム ロール**アグリーメントの設定が**レスポンダー**です。<br /><br /> これは、も必要なフィールドは、次に該当する場合 (この場合は、**アクション URL**フィールドも必須です)。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`False`します。<br /><br /> このフィールドには、"http://domain" または "https://domain" のいずれかで始まる、有効な URI を入力する必要があります。|  
|**ポート**|**同期 URL**|ホーム組織が HTTP アダプターを介して接続を確立するために使用する URL。 たとえば、http://FabrikamServer/BTARNApp/RNIFReceive.aspx。<br /><br /> このフィールドは、次の項目が該当する場合に必須です。<br /><br /> -**同期**プロセス構成設定は`True`します。<br /><br /> -**ホーム ロール**アグリーメントの設定が**イニシエーター**です。<br /><br /> このフィールドには、"http://domain" または "https://domain" のいずれかで始まる、有効な URI を入力する必要があります。|  
|**[プロトコル]**|**ダイジェスト メソッド**|否認不可を目的として、着信メッセージのダイジェストの計算に使用されるプロトコル。<br /><br /> **以降で[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]以降のバージョン**、SHA2 サポート自動的に含まれています。 オプションがあります: **MD5**、 **sha-1**、 **sha-256** (既定)、 **sha-384**、および**sha-512**です。<br /><br />以前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]バージョンでは、オプションには、 **MD5**または**sha-1** (既定値)。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信パイプラインが受信し、メッセージの暗号化に使用するプロトコル場合でもメッセージを復号化され、**エンコード**アグリーメントのこのタブの設定が一致しません。 したがって、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RC2 40 または 3 des で暗号化されたメッセージを受信します。<br /><br /> すべての送信署名付きメッセージでは、sha-1 のダイジェストがあります。|  
|**[プロトコル]**|**すべての部分をエンコードします。**|マルチパート メッセージのすべての部分を同時にエンコードするかどうかを示します。<br /><br /> `True` または `False` (既定値) を指定できます。<br /><br /> ときに`True`、マルチパート メッセージのすべての部分で示されているメソッドを使用してエンコードされます、`Encoding`プロパティです。<br /><br /> `False` を指定した場合は、`Encoding` プロパティで指定された方法に従って、添付ファイルだけがエンコードされます (添付ファイルは、`Encoding` プロパティで指定された方法に従い、送信パイプラインで常にエンコードされます)。既定では、このプロパティを `False` に設定した場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はメッセージのその他の部分 (RNIF 2.01 では 4 つの部分、RNIF 1.1 では 3 つの部分) を quoted-printable 形式でエンコードします。|  
|**[プロトコル]**|**[エンコード]**|すべての部分のエンコードに使用するプロトコル (場合、**すべての部分のエンコード**ボックスは`True`) または添付ファイル (場合、**すべての部分のエンコード**ボックスは`False`)。<br /><br /> 指定できます**8 ビット**、 **base 64** (既定)、または**引用符で囲まれたに印刷**です。|  
|**[プロトコル]**|**暗号化アルゴリズム**|着信メッセージと送信メッセージを暗号化するために使用されるアルゴリズム。<br /><br /> **以降で[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]以降のバージョン**AES のサポートは自動的に含まれます。 オプションがあります。 **RC2 40**、 **3 des**、 **AES128** (既定)、 **AES192**、および**AES256**です。 <br /><br />以前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]バージョンでは、オプションには、 **RC2 40** (既定値) または**3 des**です。<br /><br /> 暗号化アルゴリズムは、設定した場合のみ効果を受け取り、`Is Persistent Confidentiality Required`プロパティを**ペイロード**または**ペイロード コンテナー**対応するプロセスの構成にします。|  
|**[プロトコル]**|**暗号化の方向**|暗号化対象のメッセージが着信メッセージなのか、送信メッセージなのか、あるいはその両方なのかを示します。<br /><br /> 指定できます**受信**、**送信**、または**インバウンド/アウト バウンド**(既定)。<br /><br /> 暗号化の方向設定のみは有効に設定した場合、`Is Persistent Confidentiality Required`プロパティを**ペイロード**または**ペイロード コンテナー**対応するプロセスの構成にします。|  
|**カスタム プロパティ**|**名前**|カスタム プロパティの名前です。<br /><br /> カスタム プロパティはアグリーメント単位で設定します。 新しいカスタム プライベート プロセスを作成する場合、これらのカスタム プロパティをさまざまなアグリーメントの処理に使用できます。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK の `RuntimeConfig.GetTPACustomConfigValue` メソッドを使用すると、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成からカスタム プロパティを取得できます。<br /><br /> `Name` プロパティは一意であり、かつ空でない必要があります。<br /><br /> 次のカスタム値を入力できます。<br /><br /> - **[AAR]**です。 Acceptance Acknowledgment Required (要承認確認) カスタム プロパティ。 RNIF 1.1 にのみ適用されます。 これを設定して**false** (これは区別されません) のみ、受信確認、承認確認されませんを要求するようにします。 場合**AAR**以外の何もする設定**false**応答側パブリック プロセスが承認確認を送信する必要がありますし、開始側パブリック プロセスは承認確認を必要とします。 [AAR] を false に設定した場合、パブリック プロセスが完了するのは受信確認の後です。<br /><br /> - **HPCC**です。 Home Partner Classification Code (ホーム パートナー分類コード)。 RNIF 1.1 にのみ適用されます。 この値によって、送信メッセージの Service Header に含まれるホーム パートナーの GlobalPartnerClassificationCode 要素を、[値] 列のエントリに設定できます。 この値は、ホーム組織の構成において、ホーム組織の分類プロパティより優先されます。 ホーム組織で複数の分類を持つことができる場合に、このカスタム プロパティを使用します。<br /><br /> - **PPCC**です。 Partner Profile Classification Code (パートナー プロファイル分類コード)。 RNIF 1.1 にのみ適用されます。 この値によって、送信メッセージの Service Header に含まれるパートナーの GlobalPartnerClassificationCode 要素を、[Value] 列のエントリに設定できます。 この値は、パートナー構成において、パートナーの分類プロパティより優先されます。 パートナーは、複数の分類を持つことができる場合、このカスタム プロパティを使用します。|  
|**カスタム プロパティ**|**値**|カスタム プロパティの値。|  
  
### <a name="to-create-a-trading-partner-agreement"></a>取引先アグリーメントを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3.  右クリック**契約**、 をポイント**新規**、クリックして**アグリーメント**です。  
  
4.  新しいアグリーメントのプロパティ ダイアログ ボックスで、**全般**、**ポート**、**プロトコル**、および**カスタム プロパティ**タブで、値を入力します設定。 これらの設定の詳細については、上の表を参照してください。  
  
5.  **[OK]**をクリックします。  
  
    > [!NOTE]
    >  BTARN は、アグリーメントがアクティブ化されるまで、アグリーメントに関連するメッセージを受け入れません。  
  
6.  右側のウィンドウで、アグリーメントの名前を右クリックし、をクリックして**Activate**です。  
  
> [!NOTE]
>  アグリーメントが既にアクティブ化された場合、は、右側のウィンドウで、アグリーメントの名前を右クリックし、をクリックすることができます**Deactivate**から送信または受信されるアグリーメントに関連付けられているすべてのメッセージを防ぐためにします。  
  
### <a name="to-edit-a-trading-partner-agreement"></a>取引先アグリーメントを編集するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、をクリックし、**契約**ノード。  
  
3.  編集、およびをクリックするアグリーメントを右クリックして**プロパティ**です。  
  
4.   **\<** *契約名* **\>** プロパティ ダイアログ ボックスで、**全般**と**連絡先のプロパティ**タブは必要に応じて設定を変更します。 これらの設定の詳細については、上の表を参照してください。  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [BTARN 構成の管理](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)