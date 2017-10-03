---
title: "BizTalk Accelerator を SWIFT の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa9812243ef7d5ff4bb8b902ac7aee48e54ab99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-biztalk-accelerator-for-swift"></a>SWIFT の BizTalk アクセラレータを構成します。

構成、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]です。 

インストールするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成を自動的に実行できるようにする チェック ボックスがあります。 または、BizTalk Accelerator 用 SWIFT (A4SWIFT) の構成では、アプリの一覧を開くことができます。

このトピックは、構成する方法を示します、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アクセラレータ、構成とも、後の構成手順の一覧をインポートまたはエクスポートの方法です。

## <a name="configure-a4swift"></a>A4SWIFT を構成します。

1. SWIFT (A4SWIFT) の構成を BizTalk Accelerator を開きます。
2. 選択**MCRR**です。 MCRR をインストールした場合にのみ使用できますが、 **Message Repair and New Submission**コンポーネントです。
3. 確認を求められたら**を新しいデータベース グループを作成する**:

  * 示すように新しいグループを作成するには、このオプションを選択、**グループ**ウィンドウです。 
  * データベースの既存のグループを参加させるのには、このオプションをオフにします。

3. インストールした場合**Message Repair and New Submission の Web コンポーネント**選択してから、 **WebService**です。
4. A4SWIFT Web サービスをホストする web サイトを選択します。 既定では、既定の Web サイトが選択されます。
5. 選択**構成を適用**です。
6. **概要**構成設定を確認し、クリックして**構成**です。 

    > [!TIP] 
    > 必要であれば、構成設定を XML ファイルとして保存できます。

7. 選択**完了**構成が完了するとします。

## <a name="export-or-import-a-configuration"></a>エクスポートまたはインポートする構成
A4SWIFT の構成設定は、XML ファイルにエクスポートできます。 これらの設定は、別の A4SWIFT インストールを構成し、インポートできます。 

### <a name="export-the-configuration"></a>構成をエクスポートします。

1. SWIFT の構成には、Microsoft BizTalk Accelerator を開き、選択**構成のエクスポート**です。
2. **名前を付けて保存**、構成ファイルを保存するには、構成ファイルの名前を入力するフォルダーを参照し、**保存**です。
3. 正常にエクスポートされると、選択**OK**です。

### <a name="import-a-configuration"></a>構成をインポートします。
1. SWIFT の構成には、Microsoft BizTalk Accelerator を開き、選択**構成のインポート**です。
2. 構成ファイルを格納するフォルダーを参照、ファイルを選択し、**インポート**です。

## <a name="post-configuration-steps"></a>インストール後の構成手順

### <a name="add-users-to-the-a4swift-users-group"></a>A4SWIFT の Users グループにユーザーを追加します。

構成した後、 [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]、BizTalkServerApplication ホスト インスタンスを実行するアカウントを追加、 **A4SWIFT ユーザー**グループ (*いない*、 **A4SWIFT 管理者**グループ)。 

**手順**:

1. 開いている**Services**です。 使用可能なサービスも**サーバー マネージャー**、し**ツール**です。 
2. 一覧で、検索**BizTalk Service BizTalk Group: BizTalkServerApplication**です。 
3. そのプロパティを開くには、二重選択します。
4. **ログオン** タブで、ユーザー アカウントは、として表示されている**このアカウント**です。
5. 開いている**ローカル ユーザーとグループ**(コンピューターの管理) し、検索、 **A4SWIFT ユーザー**グループ。 このグループにユーザー アカウントを追加します。

> [!TIP] 
> ホスト インスタンス アカウントには、このグループのメンバーシップ Message Repair ランタイム コンポーネントのホストの BizTalk Server データベースにアクセスする必要があります。

### <a name="check-the-identity-of-the-application-pool"></a>アプリケーション プールの id を確認します。
A4SWIFT_MRSR web サービスは、IIS のアプリケーションでホストされます。 アプリケーション プール id*できません*ネットワーク サービスを使用します。 メンバーであるローカルまたはドメイン アカウントにアプリケーション プールの id を変更、 **A4SWIFT ユーザー**グループ。

**手順**:

1. 開いている**インターネット インフォメーション サービス マネージャー**です。 IIS マネージャーはでも利用できます**サーバー マネージャー**、し**ツール**です。 
2. 展開して、**既定の Web サイト**、A4SWIFT_MRSR web サービスを選択します。 
3. 選択**基本設定**です。 アプリケーション プールの名前が表示されます。
4. 左のペインで選択**アプリケーション プール**、アプリケーション プールを選択します。
5. 選択**詳細設定**、し、変更、 **Identity**必要な場合です。