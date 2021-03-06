---
title: 作成するか、契約の編集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bbe4b57-d6ec-4448-9c80-2aecd98e0dc7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 404182fda241afa6876142925ec449f1bae3c6ce
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753034"
---
# <a name="creating-or-editing-an-agreement"></a>作成するか、契約の編集
ここでは、取引先アグリーメント (TPA) の作成方法または編集方法について説明します。 取引先アグリーメントは、2 つの取引先の間に、ID、PIP (Partner Interface Process)、アクション URL、シグナル URL、同期 URL、関連付けられたプロトコルなどのリレーションシップを構成します。  

 取引先アグリーメントには、プロセス構成、ホーム組織、パートナー、およびアグリーメントに関する設定が含まれています。 アグリーメントには、これらすべての設定が必要になります。 プロセス構成は RosettaNet PIP またはカスタム スキーマのいずれに基づいて作成できますが、その場合は構成を作成する必要があります。 ホーム組織と取引先組織の両方を定義することも必要があります。 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]は不明なパーティ間のメッセージ交換をサポートしていません。  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、これらすべての設定に基づいて、メッセージを処理および検証します。 たとえば CIDX メッセージの場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は RosettaNet Implementation Framework (RNIF) のバージョン (1.1 のみ)、[0A1 アグリーメント] \(非 0A1 のみ)、および `Is Single Action` プロパティ (シングル アクションのみ) に基づいて検証を行います。 CIDX メッセージは、RNIF のバージョン「1.1」、"非 0A1"に 0A1 アグリーメントを設定する場合のみを検証し、`Is Single Action`プロパティを`True`します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] また、アグリーメントのプロパティにプロセス構成プロファイル設定と整合性があることを検証します。 たとえば、プロファイルの `Standard` プロパティが CIDX に設定されているかどうか、およびアグリーメントの [0A1 アグリーメント] プロパティが非 0A1 に設定されているかどうかが確認されます。  

 プロセスがアクティブな状態でアグリーメントを変更すると、予測不可能な結果が生じることがあります。 クリックするとすぐに、アグリーメントのプロパティへの変更が適用されます**適用**または**OK**をしたが、そのまま使用することはできません予測、プロセスのどのステージが実行されています。 アグリーメントを変更した後は、現在のプロセスの新しいアクティビティや新しいプロセスはすべて、変更されたアグリーメント プロパティを使用します。 ただし、アグリーメントを変更するときに実行中であったプロセスは、処理中のメッセージには以前のアグリーメント プロパティを既に使用していた可能性があります。  

 アグリーメントを作成したら、アクティブ化して、そのアグリーメントに関連付けられたメッセージを送信または受信できるようにする必要があります。 アグリーメントに関連付けられたメッセージが送信または受信されないように、アグリーメントを非アクティブ化することもできます。 アグリーメントを編集するには、非アクティブ化して、編集後に再度アクティブ化します。  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、この情報を BTARNCONFIG データベースの TPAConfig テーブルに保存します。  

 次の表に、取引先アグリーメントの設定をタブごとに整理して示します。既定では、最も一般的に使用される値が設定されています。 これらの設定を作成して編集するための手順は、表の後に記載されています。  


|                          タブ                           |          設定          |  使用方法  |
|---|---|---|
|                      **全般**                       |         **名前**          |  Fabrikam_To_Contoso_3A2 など、アグリーメントの一意の名前。<br /><br /> 必須フィールド。 |
|                      **全般**                       | **プロセスの構成** | PIP の識別子。<br /><br /> この番号によって、このアグリーメントに関連付けられたプロセス構成が識別されます。<br /><br /> 既定値は、プロセス構成一覧の最初に表示される値です。 ドロップダウン リストには、以前入力されたすべてのプロセス構成が含まれます。<br /><br /> 必須フィールド。 |
|                      **全般**                       |    **自分の所属組織**    |  ドロップダウン リストから選択されたホーム組織。<br /><br /> 必須フィールド。 |
|                      **全般**                       | **取引先組織**  | ドロップダウン リストから選択された取引先組織。<br /><br /> 必須フィールド。 |
|                      **全般**                       |      **[説明]**      |  取引先アグリーメントの説明。|
|                      **全般**                       |     **RNIF のバージョン**      | [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がアグリーメントの通信に使用する RNIF のバージョン。<br /><br /> **V01.10.00**または**V02.00.01** (既定)。<br /><br /> 必要があります**V01.10.00** CIDX 用です。 |
|                      **全般**                       |       **ホーム ロール**       | ホーム組織のロール。<br /><br /> 開始側ロールまたは応答側ロールを指定できます。 |
|                      **全般**                       |     **0A1 アグリーメント**     | エラーが発生した場合に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がエラー通知メッセージ (0A1 PIP) を返すかどうかを示します。<br /><br /> **0A1** (既定値) または**0A1**します。<br /><br /> 必要があります**0A1** CIDX 用です。 |
|                      **全般**                       |         **使用方法**         | アグリーメントが使用するシナリオの種類を示します。<br /><br /> **テスト**(既定値) または**運用**します。 |
| **全般**<br /><br /> (**アプリケーション アダプター**領域) |     **アセンブリ名**     | ファイル システムから選択できる ApplicationAdapter のファイル名。<br /><br /> 既定値は空の文字列です。  |
| **全般**<br /><br /> (**アプリケーション アダプター領域**) |      **クラス名**       | [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が使用する ApplicationAdapter のクラス名。<br /><br /> 既定値は\<none\>します。 |
| **全般**<br /><br /> (**検証アダプター領域**)  |     **アセンブリ名**     | ファイル システムから選択できる ValidationAdapter のファイル名。 既定値は空の文字列です。  |
| **全般**<br /><br /> (**検証アダプター領域**)  |      **クラス名**       | [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が使用する ValidationAdapter のクラス名。<br /><br /> 既定値は\<none\>します。 |
|                       **ポート**                        |      **アクションの URL**       | ホーム組織がアクション メッセージを送信する先の URL。 たとえば、 `http://FabrikamServer/BTARNApp/RNIFReceive.aspx` のようにします。<br /><br /> このフィールドは、次の項目がすべて該当する場合に必須です。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`True`します。<br /><br /> -**ホーム ロール**アグリーメントの設定が**イニシエーター**します。<br /><br /> これは必須フィールド場合も、次に該当する (この場合は、**シグナル URL**フィールドも必須です)。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`False`します。<br /><br /> -このフィールドには、いずれかのいずれかで始まる有効な URI を入力する必要があります"<`http://domain`>"または"<`https://domain`>"。  |
|                       **ポート**                        |      **シグナル URL**       | ホーム組織がシグナル メッセージを送信する先の URL。 たとえば、 `http://FabrikamServer/BTARNApp/RNIFReceive.aspx` のようにします。<br /><br /> このフィールドは、次の項目が該当する場合に必須です。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`True`します。<br /><br /> -**ホーム ロール**アグリーメントの設定が**レスポンダー**します。<br /><br /> これは必須フィールド場合も、次に該当する (この場合は、**アクション URL**フィールドも必須です)。<br /><br /> -**同期**プロセス構成設定は`False`します。<br /><br /> -**シングル アクション**プロセス構成設定は`False`します。<br /><br /> このフィールドには、いずれかのいずれかで始まる有効な URI を入力する必要があります"<`http://domain`>"または"<`https://domain`>"。  |
|                       **ポート**                        |       **同期 URL**        | ホーム組織が HTTP アダプターを介して接続を確立するために使用する URL。 たとえば、 `http://FabrikamServer/BTARNApp/RNIFReceive.aspx` のようにします。<br /><br /> このフィールドは、次の項目が該当する場合に必須です。<br /><br /> -**同期**プロセス構成設定は`True`します。<br /><br /> -**ホーム ロール**アグリーメントの設定が**イニシエーター**します。<br /><br /> このフィールドには、いずれかのいずれかで始まる有効な URI を入力する必要があります"<`http://domain`>"または"<`https://domain`>"。  |
|                      **[プロトコル]**                      |     **ダイジェストの作成方法**     | 否認不可を目的として、着信メッセージのダイジェストの計算に使用されるプロトコル。<br /><br /> **以降で[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]以降のバージョン**、SHA2 サポートが自動的に含まれます。 オプションがあります: **MD5**、 **sha-1**、 **SHA 256** (既定)、 **sha-384**、および**sha-512**します。<br /><br />以前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]オプションがあります。 バージョンは、 **MD5**または**sha-1** (既定値)。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信パイプラインが受信し、メッセージの暗号化に使用するプロトコル場合でも、メッセージを復号化、および**エンコード**アグリーメントのこのタブの設定が一致しません。 そのため、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RC2 40 または 3 des で暗号化されたメッセージを受信します。<br /><br /> すべての送信署名付きメッセージでは、sha-1 のダイジェストがあります。 |
|                      **[プロトコル]**                      |   **すべての部分をエンコードします。**    | マルチパート メッセージのすべての部分を同時にエンコードするかどうかを示します。<br /><br /> `True` または `False` (既定値) を指定できます。<br /><br /> ときに`True`で指定された方法を使用して、マルチパート メッセージのすべての部分がエンコードされる、`Encoding`プロパティ。<br /><br /> `False` を指定した場合は、`Encoding` プロパティで指定された方法に従って、添付ファイルだけがエンコードされます (添付ファイルは、`Encoding` プロパティで指定された方法に従い、送信パイプラインで常にエンコードされます)。既定では、このプロパティを `False` に設定した場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はメッセージのその他の部分 (RNIF 2.01 では 4 つの部分、RNIF 1.1 では 3 つの部分) を quoted-printable 形式でエンコードします。 |
|                      **[プロトコル]**                      |       **[エンコード]**        | すべての部分のエンコードに使用するプロトコル (場合、**すべての部分のエンコード**ボックスは`True`) または添付ファイル (場合、**すべての部分のエンコード**ボックスは`False`)。<br /><br /> **8 ビット**、 **base 64** (既定)、または**引用符で囲まれた印刷可能な**します。 |
|                      **[プロトコル]**                      | **暗号化アルゴリズム**  | 着信メッセージと送信メッセージを暗号化するために使用されるアルゴリズム。<br /><br /> **以降で[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]以降のバージョン**AES のサポートが自動的に含まれます。 オプションがあります。 **RC2 40**、 **3 des**、 **AES128** (既定)、 **AES192**、および**AES256**します。 <br /><br />以前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]オプションがあります。 バージョンは、 **RC2 40** (既定値) または**3 des**します。<br /><br /> 暗号化アルゴリズムは、設定した場合のみ効果を与える、`Is Persistent Confidentiality Required`プロパティを**ペイロード**または**ペイロード コンテナー**で対応するプロセスの構成。 |
|                      **[プロトコル]**                      | **暗号化の方向**  |  暗号化対象のメッセージが着信メッセージなのか、送信メッセージなのか、あるいはその両方なのかを示します。<br /><br /> **受信**、**送信**、または**インバウンド/アウト バウンド**(既定)。<br /><br /> 暗号化の方向設定は、設定した場合のみ効果を与える、`Is Persistent Confidentiality Required`プロパティを**ペイロード**または**ペイロード コンテナー**で対応するプロセスの構成。 |
|                 **カスタム プロパティ**                  |         **名前**          | カスタム プロパティの名前です。<br /><br /> カスタム プロパティはアグリーメント単位で設定します。 新しいカスタム プライベート プロセスを作成する場合、これらのカスタム プロパティをさまざまなアグリーメントの処理に使用できます。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK の `RuntimeConfig.GetTPACustomConfigValue` メソッドを使用すると、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成からカスタム プロパティを取得できます。<br /><br /> `Name` プロパティは一意であり、かつ空でない必要があります。<br /><br /> 次のカスタム値を入力できます。<br /><br /> - **AAR**します。 Acceptance Acknowledgment Required (要承認確認) カスタム プロパティ。 RNIF 1.1 にのみ適用されます。 これを設定**false** (大文字小文字が区別はない) にのみ受信確認、承認確認ではない必要があります。 場合**AAR**以外の値に設定されて**false**応答側パブリック プロセスが承認確認を送信する必要がありますし、開始側パブリック プロセスは承認確認を必要とします。 [AAR] を false に設定した場合、パブリック プロセスが完了するのは受信確認の後です。<br /><br /> - **HPCC**します。 Home Partner Classification Code (ホーム パートナー分類コード)。 RNIF 1.1 にのみ適用されます。 この値によって、送信メッセージの Service Header に含まれるホーム パートナーの GlobalPartnerClassificationCode 要素を、[値] 列のエントリに設定できます。 この値は、ホーム組織の構成において、ホーム組織の分類プロパティをオーバーライドします。 ホーム組織で複数の分類を持つことができる場合に、このカスタム プロパティを使用します。<br /><br /> - **PPCC**します。 Partner Profile Classification Code (パートナー プロファイル分類コード)。 RNIF 1.1 にのみ適用されます。 この値によって、送信メッセージの Service Header に含まれるパートナーの GlobalPartnerClassificationCode 要素を、[Value] 列のエントリに設定できます。 この値は、パートナー構成において、パートナーの分類プロパティをオーバーライドします。 パートナーが 1 つ以上の分類がある場合に、このカスタム プロパティを使用します。 |
|                 **カスタム プロパティ**                  |         **[値]**         |  カスタム プロパティの値。 |

## <a name="create-a-trading-partner-agreement"></a>取引先アグリーメントを作成します。  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  

2. BTARN 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  

3. 右クリックして**契約**、 をポイント**新規**、順にクリックします**契約**します。  

4. 新しいアグリーメントのプロパティ ダイアログ ボックスで、上、**全般**、**ポート**、**プロトコル**、および**カスタム プロパティ**タブで、値を入力します設定。 これらの設定の詳細については、上の表を参照してください。  

5. **[OK]** をクリックします。  

   > [!NOTE]
   >  BTARN は、アグリーメントがアクティブ化されるまで、アグリーメントに関連するメッセージを受け入れません。  

6. 右側のウィンドウで、アグリーメントの名前を右クリックし、をクリックし、 **Activate**します。  

> [!NOTE]
>  アグリーメントが既にアクティブ化された場合、は、右側のウィンドウで、アグリーメントの名前を右クリックし をクリックすることができます**非アクティブ化**から送信または受信されるアグリーメントに関連付けられているすべてのメッセージを防ぐためにします。  

## <a name="edit-a-trading-partner-agreement"></a>取引先パートナー契約を編集します。  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  

2. BTARN 管理コンソールで、[展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、] をクリックし、**契約**ノード。  

3. 編集するをクリックするアグリーメントを右クリックして**プロパティ**します。  

4. **\<**<em>契約名</em>**\>** プロパティ ダイアログ ボックスで、**全般**と**連絡先のプロパティ**タブは必要に応じて設定を変更します。 これらの設定の詳細については、上の表を参照してください。  

5. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [BTARN 構成の管理](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)
