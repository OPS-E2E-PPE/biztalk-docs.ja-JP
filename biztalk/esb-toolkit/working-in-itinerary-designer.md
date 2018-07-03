---
title: Itinerary Designer での作業 |Microsoft Docs
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
ms.openlocfilehash: 747ce8a750f2b2c775deaa1123a1b6b1d387eafc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999403"
---
# <a name="working-in-itinerary-designer"></a>Itinerary Designer での作業
Microsoft Visual c# プロジェクトを作成した後は、スケジュールの新しいモデルを作成し、プロジェクトに既存のスケジュールを追加します。 次の手順では、新しいスケジュールを作成、スケジュールの既存のモデルを追加またはスケジュールの名前を変更する方法について説明します。  
  
> [!NOTE]
>  旅行プラン デザイナーを使用する前から Microsoft.Practices.ESB.CORE Windows インストーラー (.msi ファイル) をインストールする必要があります、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]フォルダーをインストールします。 この手順では、グローバル アセンブリ キャッシュに必要なランタイムのアセンブリをインストールします。  
  
## <a name="basic-operations"></a>基本的な操作  

#### <a name="create-an-itinerary"></a>スケジュールを作成します。  
  
1.  ソリューション エクスプ ローラーで、c# のプロジェクト名を右クリックして**追加**、 をクリックし、**新しい行程**。  
  
2.  **名前** ダイアログ ボックスの下部にあるボックスで、スケジュールの名前を入力し、 をクリックし、**追加**します。  
  
    > [!NOTE]
    >  新しいスケジュールが作成され、旅行プランのデザイナーに表示されると、対応する .itinerary ファイルが作成され、ソリューション エクスプ ローラーで表示されます。  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a>既存のスケジュールをプロジェクトに追加します。
  
1.  ソリューション エクスプ ローラーで右クリックで、c# のプロジェクト名をポイントして**追加**、 をクリックし、**既存項目の**します。  
  
2.  **既存項目の追加** ダイアログ ボックスでは、旅行プランを itinerary、クリックを格納するディレクトリに移動し、順にクリックします**追加**します。  
  
    > [!NOTE]
    >  旅行プランは、プロジェクトに追加されます。  
  
#### <a name="change-the-name-of-an-itinerary"></a>スケジュールの名前を変更します。  
  
1.  ソリューション エクスプ ローラーでクリックして、名前を変更する .itinerary ファイルを右クリックして**の名前を変更**します。  
  
2.  新しいファイル名を入力し、ENTER キーを押します。  
  
#### <a name="save-an-itinerary"></a>スケジュールを保存します。  
  
**ファイル** メニューのをクリックして**保存\<itinerary 名前\>** します。  
  
> [!NOTE]
>  スケジュール オンランプ ファイルは、対応する XML 形式で DSL モデルとして保存されます。  
  
#### <a name="set-itinerary-export-properties"></a>スケジュール オンランプ エクスポート プロパティを設定します。  
  
1. プロパティ ウィンドウで、入力、**名前**プロパティ。  
  
2. プロパティ ウィンドウで、入力、**バージョン**プロパティ。  
  
3. プロパティ ウィンドウで、指定、**は要求の応答**プロパティのドロップダウン リストを使用します。 このプロパティを設定**true**場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]入り口とクライアント アプリケーションが通信する要求-応答メッセージ交換パターンを使用します。  
  
4. [プロパティ] ウィンドウで次のように設定します。、**エクスポート モード**プロパティを**既定**または**Strict**します。  
  
   > [!NOTE]
   >  作成するときに[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]日程、旅行プラン デザイナーを使用して、**エクスポート モード**サービスを実行する場所を定義するプロパティを使用できます。 設定、**エクスポート モード**プロパティを**Strict**旅行計画により、規定されたコンテナー内で実行されます XML 行程で各スケジュール サービスのステージのプロパティがここでは、を。サービスが実行されるパイプラインを指定します。 このプロパティ設定されている場合**既定**、指定されていない段階に、Microsoft ESB と互換性のあるスケジュールが作成され、規定されている順序で、必要なパイプラインのステージでは必ずしもスケジュール サービスを実行します。  
  
#### <a name="export-an-itinerary-to-a-file"></a>日程をファイルにエクスポートします。  
  
1.  [プロパティ] ウィンドウで次のようにクリックします。 **XML 行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。  
  
2.  [プロパティ] ウィンドウで次のように設定します。、**旅行プラン XML ファイル**プロパティを新しい値。  
  
#### <a name="export-an-itinerary-to-a-database"></a>日程をデータベースにエクスポートします。  
  
1. [プロパティ] ウィンドウで次のようにクリックします。**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。  
  
2. [プロパティ] ウィンドウで次のように設定します。、**行程データベース**行程データベースを指す接続文字列のプロパティ。  
  
3. [プロパティ] ウィンドウで次のように設定します。、**行程状態**プロパティを**Published**または**配置済み**。  
  
   > [!NOTE]
   >  データベースに、旅行プランをエクスポートするときに**行程状態**に設定**発行済み**、有効にならないスケジュールは、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] に、プロパティの設定後までの時間を実行**デプロイされた**します。  
  
## <a name="security-operations"></a>セキュリティの操作  
 格納されているパスワードおよびその他の資格情報など、旅行プラン デザイナーを使用して、機密情報を保護することができます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] X.509 証明書を使用してこの情報を暗号化することで、スケジュールします。  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a>スケジュールを X.509 証明書を選択します。  
  
1.  旅行プラン デザイナーのプロパティ ウィンドウで、**暗号化証明書**プロパティ、およびクリック、**ストアの場所**ドロップダウン リスト、および選択、 **CurrentUser**または**LocalMachine**します。 これにより、X.509 証明書ストアが、現在のユーザーまたはローカル コンピューターに関連付けられます。  
  
2.  [プロパティ] ウィンドウ、**ストア名**ドロップダウン リストと、証明書ストアに対応する値を選択します。  
  
3.  プロパティ ウィンドウで、暗号化証明書のプロパティの横にある省略記号ボタン (…) をクリックし、選択、 **X.509 証明書**で、**証明書の選択** ダイアログ ボックス。  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a>日程から X.509 証明書を削除します。  
  
- 旅行プラン デザイナーのプロパティ ウィンドウで、**暗号化証明書**プロパティ、および設定して、**ストアの場所**プロパティを別の値。 これで、古い証明書の関連付けを解除、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary モデル。  
  
#### <a name="disable-the-x509-certificate-validation"></a>X.509 証明書の検証を無効にします。  
  
レジストリ エディターでは、サブキーに移動**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**、し、設定、 **RequireX509Certificate**プロパティの値を**false**します。  
  
> [!NOTE]
>  インストールした場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サブキーは、64 ビット サポートしているオペレーティング システムで**HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**します。