---
title: Microsoft Windows Communication Foundation 行 of Business Adapter SDK のドキュメント |Microsoft Docs
description: クイック リンクをインストール、概要、計画し設計、開発、および BizTalk Server で WCF LOB Adapter SDK のトラブルシューティング
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
ms.openlocfilehash: 7dbfd4454e2380c44b2ccf03adb61cd2afa84fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363482"
---
# <a name="microsoft-windows-communication-foundation-line-of-business-adapter-sdk-documentation"></a>Microsoft Windows Communication Foundation 行 of Business Adapter SDK のドキュメント
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメントには、開発、デプロイ、およびで作成されたアダプターを使用するのに役立つリソースが含まれています、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  

## <a name="about-the-sdk"></a>SDK の詳細について  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプター開発者に役立つツールは、WCF を使用して既存の LOB システムへのサービス指向のインターフェイスを作成および実行時エンジンのコレクションです。 SDK の目的は、互いを統合するには、エンタープライズ アプリケーション、データベース、およびメッセージング プラットフォームを有効にする再利用可能なメタデータ中心の WCF ベース アダプターの一貫した開発を促進します。  
  
 この WCF ベースの SDK には、WCF バインドとして LOB システムにアダプターが表示されます。 一般的な WCF サービスのように、アダプターのコンシューマーでは、アダプターにアクセスできます。コンシューマーを新しいプログラミング モデルを確認する必要はありません。 カスタムの .NET アプリケーションを含む複数の .NET アプリケーションで開発された同じアダプターを再利用できる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SharePoint、および Microsoft SQL Server Integration Services (SSIS) と、アダプター開発者提供: ADO.NET の shim を使用します。 メタデータ参照、検索、および検索機能です。 さらに、アダプターを提供しますアダプターのコンシューマーは、LOB システムのライブの型をモデル化を反映する WCF コントラクトを選択的に生成できます。  
 
## <a name="readme"></a>Readme
![コミュニティ リソース アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "コミュニティ") [Readme とプライバシー](../../adapters-and-accelerators/wcf-lob-adapter-sdk/readme-and-privacy-in-the-wcf-lob-adapter-sdk.md) SDK に含まれるコンポーネントについて説明しますと、プライバシー オプションについて説明します。 

## <a name="install"></a>インストール
![作業の開始アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [WCF LOB Adapter SDK をインストール](../../adapters-and-accelerators/wcf-lob-adapter-sdk/install-the-wcf-lob-adapter-sdk.md)をインストールして、SDK をアンインストールする、カスタム アダプターを削除し、サイレントを行う手順を示しますインストールします。 

## <a name="get-started"></a>作業開始
![作業の開始アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [の概要、WCF LOB アダプター SDK を使用した](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)は、に新しいユーザーのいくつかの一般的な情報が含まれています[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]概念の読み取りや一部のチュートリアルなど。 
  
## <a name="plan-and-design"></a>計画と設計 
![アダプター アーキテクチャ アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [計画と設計を WCF LOB Adapter SDK を使用してアダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)アダプター、チャネル、またはサービスを使用するタイミングを説明します。 また、URI、トランザクションの概要をデザイン、サポートされているメッセージング パターンについて説明します。

## <a name="develop-and-create"></a>開発し、作成
![アダプタ開発アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [開発 WCF LOB Adapter SDK を使用して、アダプターを作成または](../../adapters-and-accelerators/wcf-lob-adapter-sdk/develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk.md)のベスト プラクティスを一覧表示のガイダンスを提供します。バージョン管理、認証、および詳細。

## <a name="gac-and-deploy"></a>GAC とデプロイ
![アダプター サンプル アイコン](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a")次の手順が GAC に追加して、machine.config を更新、展開パッケージを作成するには、アダプターを作成した後。 [WCF LOB Adapter SDK を使用してアダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-adapter-using-the-wcf-lob-adapter-sdk.md)この情報が含まれています。

## <a name="troubleshoot"></a>[トラブルシューティング]
![アダプタのトラブルシューティング アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [WCF LOB Adapter SDK を使用して作成されたトラブルシューティング アダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)パフォーマンスを使用するトレースを有効にする手順を示しますカウンター、および WSDL を生成します。

