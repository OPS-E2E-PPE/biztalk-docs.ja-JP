---
title: BizTalk Accelerator for SWIFT に構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fff8f5aeebba2f9734f29ae929d23845431da7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378827"
---
# <a name="configure-biztalk-accelerator-for-swift"></a>BizTalk Accelerator for SWIFT に構成します。

構成、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]します。 

インストールするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成を自動的に実行できるようにするチェック ボックスがあります。 または、BizTalk Accelerator for SWIFT (A4SWIFT) 構成がアプリで表示を開くことができます。

このトピックでは、構成する方法を示します、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アクセラレータをエクスポートまたはインポートする構成では、また構成後の手順をリストする方法。

## <a name="configure-a4swift"></a>A4SWIFT を構成します。

1. SWIFT (A4SWIFT) の構成には、BizTalk Accelerator を開きます。
2. 選択**MCRR**します。 MCRR をインストールした場合にのみ使用できますが、 **Message Repair and New Submission**コンポーネント。
3. 求められたら**新しいデータベース グループを作成したい**:

   * 示すように新しいグループを作成するには、このオプションを選択、**グループ**ウィンドウ。 
   * 既存のデータベース グループに参加するには、このオプションをオフにします。

4. インストールした場合**Message Repair and New Submission の Web コンポーネント**を選択し、 **WebService**します。
5. A4SWIFT Web サービスをホストする web サイトを選択します。 既定では、既定の Web サイトを選択します。
6. 選択**構成の適用**します。
7. **概要**構成の設定を確認し、クリックして**構成**します。 

    > [!TIP] 
    > 必要な場合は、構成設定を XML ファイルとして保存できます。

8. 選択**完了**構成が完了したとき。

## <a name="export-or-import-a-configuration"></a>エクスポートまたはインポートの構成
A4SWIFT の構成設定は、XML ファイルにエクスポートできます。 これらの設定は、A4SWIFT インストール環境別の構成をインポートできます。 

### <a name="export-the-configuration"></a>構成をエクスポートします。

1. SWIFT の構成では、Microsoft BizTalk Accelerator を開き、選択**構成のエクスポート**します。
2. **名前を付けて保存**、構成ファイルを保存、構成ファイルの名前を入力するフォルダーを参照し、**保存**します。
3. 正常にエクスポートされると、選択**OK**します。

### <a name="import-a-configuration"></a>構成をインポートします。
1. SWIFT の構成では、Microsoft BizTalk Accelerator を開き、選択**構成のインポート**します。
2. 構成ファイルを含むフォルダーを参照、ファイルを選択および選択**インポート**します。

## <a name="post-configuration-steps"></a>構成後の手順

### <a name="add-users-to-the-a4swift-users-group"></a>A4SWIFT ユーザーのグループにユーザーを追加します。

構成した後、 [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]、BizTalkServerApplication ホスト インスタンスを実行するアカウントを追加、 **A4SWIFT ユーザー**グループ (*いない*、 **A4SWIFT 管理者**グループ)。 

**手順**:

1. 開いている**サービス**します。 使用できるサービスも**サーバー マネージャー**、し**ツール**します。 
2. 一覧で、検索**BizTalk Service BizTalk Group:[Biztalkserverapplication]** します。 
3. そのプロパティを開くには、二重選択します。
4. **ログオン**メモとして表示されているユーザー アカウントのタブ**このアカウント**します。
5. 開いている**ローカル ユーザーとグループ**(コンピューターの管理) で見つけて、 **A4SWIFT ユーザー**グループ。 このグループにユーザー アカウントを追加します。

> [!TIP] 
> ホスト インスタンス アカウントには、BizTalk Server データベースにアクセスするホストのメッセージの修復のランタイム コンポーネントのこのグループ メンバーシップが必要があります。

### <a name="check-the-identity-of-the-application-pool"></a>アプリケーション プールの id を確認します。
A4SWIFT_MRSR web サービスは、IIS のアプリケーションでホストされます。 アプリケーション プール id*できません*ネットワーク サービスを指定します。 メンバーであるローカルまたはドメイン アカウントにアプリケーション プールの id を変更、 **A4SWIFT ユーザー**グループ。

**手順**:

1. 開いている**インターネット インフォメーション サービス マネージャー**します。 IIS マネージャーも記載されて**サーバー マネージャー**、し**ツール**します。 
2. 展開、**既定の Web サイト**A4SWIFT_MRSR の web サービスを選択します。 
3. 選択**基本設定**します。 アプリケーション プールの名前が表示されます。
4. 左側のウィンドウで次のように選択します。**アプリケーション プール**、し、アプリケーション プールを選択します。
5. 選択**詳細設定**、変更、 **Identity**必要な場合。