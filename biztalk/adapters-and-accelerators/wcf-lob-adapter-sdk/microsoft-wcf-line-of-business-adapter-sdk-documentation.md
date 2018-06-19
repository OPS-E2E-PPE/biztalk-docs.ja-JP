---
title: Microsoft Windows Communication Foundation の行のビジネス アダプター SDK のドキュメント |Microsoft ドキュメント
description: リンクをインストール、開始、計画し設計、開発、および BizTalk Server で WCF LOB Adapter SDK のトラブルシューティング
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2b098c-ef41-4cc0-8063-1fd043f1176f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8472fb56beab8f6d86ff33bebb9171d09d503ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225826"
---
# <a name="microsoft-windows-communication-foundation-line-of-business-adapter-sdk-documentation"></a>Microsoft Windows Communication Foundation の行のビジネス アダプター SDK のドキュメント
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメントには、開発、配置、およびで作成されたアダプターを使用するのに役立つリソースが含まれています、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  

## <a name="about-the-sdk"></a>SDK について  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム エンジンのコレクションは、アダプター開発者を支援するツールは、WCF を使用して既存の LOB システムにサービス指向のインターフェイスを作成します。 SDK の目的は、相互に統合するには、エンタープライズ アプリケーション、データベース、およびメッセージング プラットフォームを有効にする再利用可能なメタデータ中心、WCF ベース アダプターの一貫した開発を促進を開始します。  
  
 この WCF ベースの SDK では、WCF バインドとしての LOB システムにアダプターを表示します。 一般的な WCF サービスと同様に、アダプターのコンシューマー、アダプターにアクセスできます。コンシューマーは新しいプログラミング モデルがありません。 カスタム .NET アプリケーションを含む複数の .NET アプリケーションで開発された同じアダプターを再利用できる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SharePoint、および Microsoft SQL Server Integration Services (SSIS)、アダプター開発者提供: ADO.NET の shim をします。 また、アダプターにより、メタデータ参照、検索、および検索機能です。アダプターのコンシューマーは、LOB システムのライブの種類のモデリングを反映する WCF コントラクトを選択的に生成できます。  
 
## <a name="readme"></a>Readme
![コミュニティ リソース アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "コミュニティ") [Readme とプライバシー](../../adapters-and-accelerators/wcf-lob-adapter-sdk/readme-and-privacy-in-the-wcf-lob-adapter-sdk.md) SDK に含まれているコンポーネントについて説明しますと、プライバシー オプションについて説明します。 

## <a name="install"></a>Install
![はじめに アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [WCF LOB Adapter SDK をインストール](../../adapters-and-accelerators/wcf-lob-adapter-sdk/install-the-wcf-lob-adapter-sdk.md)インストールと SDK をアンインストールし、カスタム アダプターを削除しては手順を一覧表示します。サイレント インストール。 

## <a name="get-started"></a>作業を開始します。
![はじめにアイコン](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [の概要、WCF LOB Adapter SDK と](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)に慣れているユーザーの役に立つ情報が含まれています[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、概念の読み取りといくつかのチュートリアルが含まれています。 
  
## <a name="plan-and-design"></a>計画と設計 
![アダプター アーキテクチャ アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [計画と設計を WCF LOB Adapter SDK を使用してアダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)アダプター、チャネル、またはサービスを使用する場合の説明. URI、理解トランザクション、およびその他の設計は、サポートされているメッセージング パターンについても確認します。

## <a name="develop-and-create"></a>開発し、作成
![アダプター開発アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [開発 WCF LOB Adapter SDK を使用して、アダプターを作成または](../../adapters-and-accelerators/wcf-lob-adapter-sdk/develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk.md)に関するガイダンスを示します、ベスト プラクティスを一覧表示されますバージョン管理、認証、およびその他。

## <a name="gac-and-deploy"></a>GAC および展開
![アダプター サンプル アイコン](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a")次の手順は、machine.config の更新を展開パッケージを作成、GAC に追加するアダプターを作成した後です。 [WCF LOB Adapter SDK を使用してアダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-adapter-using-the-wcf-lob-adapter-sdk.md)この情報が含まれています。

## <a name="troubleshoot"></a>[トラブルシューティング]
![アダプタのトラブルシューティング アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [WCF LOB Adapter SDK を使用して作成されたトラブルシューティング アダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)リストが有効にする手順を使用してトレースでは、パフォーマンス カウンター、および WSDL を生成します。

