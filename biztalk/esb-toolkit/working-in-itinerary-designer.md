---
title: Itinerary Designer での作業 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf474c68d91b7648f7f0efcfe4e85e7531e4aa1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976784"
---
# <a name="working-in-itinerary-designer"></a>Itinerary Designer での作業
Microsoft Visual c# プロジェクトを作成した後は、新しい itinerary モデルを作成し、既存の日程をプロジェクトに追加します。 次の手順では、新しい旅程を作成、既存の itinerary モデルを追加または日程の名前を変更する方法について説明します。  
  
> [!NOTE]
>  行程デザイナーを使用する前から Microsoft.Practices.ESB.CORE Windows インストーラー (.msi ファイル) をインストールする必要があります、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]フォルダーをインストールします。 このステップでは、グローバル アセンブリ キャッシュに必要なランタイムのアセンブリをインストールします。  
  
## <a name="basic-operations"></a>基本的な操作  

#### <a name="create-an-itinerary"></a>日程を作成します。  
  
1.  ソリューション エクスプ ローラーで、c# プロジェクトの名前を右クリックし、**追加**、クリックして**新しい行程**です。  
  
2.  **名前** ダイアログ ボックスの下部にあるボックスで、旅行計画の名前を入力し、をクリックして**追加**です。  
  
    > [!NOTE]
    >  新しい行程作成されて行程デザイナーに表示され、対応する .itinerary ファイルが作成され、ソリューション エクスプ ローラーで表示されます。  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a>既存の日程をプロジェクトに追加します。
  
1.  ソリューション エクスプ ローラーで右クリックし、c# のプロジェクト名、 をポイント**追加**、クリックして**既存項目の**します。  
  
2.  **既存項目の追加** ダイアログ ボックスが、itinerary を itinerary、クリックを含むディレクトリに移動し、をクリックして**追加**です。  
  
    > [!NOTE]
    >  旅行計画は、プロジェクトに追加されます。  
  
#### <a name="change-the-name-of-an-itinerary"></a>日程の名前を変更します。  
  
1.  ソリューション エクスプ ローラーでファイルを右クリック、.itinerary、名前を変更し、をクリックする**の名前を変更**です。  
  
2.  新しいファイル名を入力し、ENTER キーを押します。  
  
#### <a name="save-an-itinerary"></a>日程を保存します。  
  
**ファイル** メニューのをクリックして**保存\<itinerary 名前\>** です。  
  
> [!NOTE]
>  Itinerary ファイルは、対応する XML 形式での DSL モデルとして保存されます。  
  
#### <a name="set-itinerary-export-properties"></a>Itinerary エクスポート プロパティを設定します。  
  
1.  [プロパティ] ウィンドウで次のように入力します。、**名前**プロパティです。  
  
2.  [プロパティ] ウィンドウで次のように入力します。、**バージョン**プロパティです。  
  
3.  プロパティ ウィンドウで、指定、**は要求の応答**プロパティのドロップダウン リストを使用します。 このプロパティを設定**true**場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]入り口と通信するクライアント アプリケーション要求-応答メッセージ交換パターンを使用します。  
  
4.  [プロパティ] ウィンドウで、設定、**エクスポート モード**プロパティを**既定**または**Strict**です。  
  
    > [!NOTE]
    >  作成するときに[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]旅程行程デザイナーを使用して、**エクスポート モード**サービスが実行されますを定義するプロパティを使用できます。 設定、**エクスポート モード**プロパティを**Strict** itinerary により指定されたコンテナー内で実行されます; XML 行程内の各 itinerary サービスのステージのプロパティがここをサービスを実行するパイプラインを指定します。 このプロパティ設定されている場合**既定**ありません段階を指定すると、日程 Microsoft ESB と互換性が作成、および itinerary サービスが、設定されている順番では必ずしも必要なパイプラインのステージでを実行します。  
  
#### <a name="export-an-itinerary-to-a-file"></a>日程をファイルにエクスポートします。  
  
1.  [プロパティ] ウィンドウでをクリックして**XML 行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。  
  
2.  [プロパティ] ウィンドウで、設定、**行程 XML ファイル**プロパティを新しい値にします。  
  
#### <a name="export-an-itinerary-to-a-database"></a>データベースに日程をエクスポートします。  
  
1.  [プロパティ] ウィンドウでをクリックして**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。  
  
2.  [プロパティ] ウィンドウで、設定、**行程データベース**行程データベースを指す接続文字列のプロパティです。  
  
3.  [プロパティ] ウィンドウで、設定、**行程ステータス**プロパティを**公開済み**または**配置済み**です。  
  
    > [!NOTE]
    >  日程を持つデータベースにエクスポートするときに**行程ステータス**に設定**Published**、itinerary を有効になりませんが、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] にプロパティを設定した後にするまでの時間を実行**展開**です。  
  
## <a name="security-operations"></a>セキュリティの操作  
 行程デザイナーを使用すると、パスワードおよびその他の資格情報に格納されているなど、機密性の高い情報を保護できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary、X.509 証明書を使用してこの情報を暗号化することによりします。  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a>日程の X.509 証明書を選択します。  
  
1.  行程デザイナーのプロパティ ウィンドウで、展開、**暗号化証明書**プロパティをクリックして、**ストアの場所**ドロップダウン リストから、 **CurrentUser**または**LocalMachine**です。 これにより、X.509 証明書ストアが現在のユーザーまたはローカル コンピューターに関連付けられます。  
  
2.  [プロパティ] ウィンドウ、**ストア名**ドロップダウン リストと、証明書ストアに対応する値を選択します。  
  
3.  プロパティ ウィンドウで、暗号化証明書プロパティの横にある省略記号ボタン (...) をクリックし、選択、 **X.509 証明書**で、**証明書の選択** ダイアログ ボックス。  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a>日程から X.509 証明書を削除します。  
  
-   行程デザイナーのプロパティ ウィンドウで、展開、**暗号化証明書**プロパティ、および設定、**ストアの場所**プロパティを別の値。 これで、古い証明書の関連付けを解除、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary モデル。  
  
#### <a name="disable-the-x509-certificate-validation"></a>X.509 証明書の検証を無効にします。  
  
レジストリ エディターでは、サブキーに移動**hkey_local_machine ESB Toolkit\2.0\Designer**、し、設定、 **RequireX509Certificate**プロパティの値を**false**です。  
  
> [!NOTE]
>  インストールした場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サブキーは、64 ビット サポートしているオペレーティング システムで**HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**です。