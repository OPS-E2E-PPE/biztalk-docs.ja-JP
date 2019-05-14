---
title: Readme と WCF LOB Adapter SDK でプライバシー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 539a88f9-ce59-46e6-8c9a-418484eabff4
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0edaa14431f1d75260958c1b145f1ec24ede5b08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363395"
---
# <a name="readme-and-privacy-in-the-wcf-lob-adapter-sdk"></a>Readme と WCF LOB Adapter SDK のプライバシー
業務 (LOB) アダプター ソフトウェア開発キット (SDK) の Windows Communication Foundation (WCF) の行  
  
## <a name="inside-the-sdk"></a>SDK 内  
 次の表で WCF LOB Adapter SDK のさまざまなコンポーネントの内容を表示する、\<インストール フォルダー\>セットアップ後にします。  
  
|型|場所|説明|  
|----------|--------------|-----------------|  
|実行時|\<インストール フォルダー\> \Bin\Microsoft.ServiceModel.Channels.dll<br /><br /> \<インストール フォルダー\> \Bin\Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse.dll|これらのアセンブリには、実行時に、ツール内で使用されるメイン フォームのコンポーネントを含むベースが含まれます。|  
|ツール|\<インストール フォルダー\> \Tools\Microsoft.ServiceModel.Channels.Tools.PlugInPackage.dll<br /><br /> \<インストール フォルダー\> \Tools\Microsoft.ServiceModel.Channels.Tools.BizTalkExtension.dll<br /><br /> \<インストール フォルダー\> \Tools\Microsoft.ServiceModel.Channels.Wizards.dll|**アダプター サービス参照を Visual Studio プラグインの追加します。**<br /><br /> (.NET プロジェクト [右] アダプター サービス参照の追加)<br /><br /> **アダプターを使用するサービスの BizTalk プロジェクト アドイン**<br /><br /> (BizTalk プロジェクト [右]、生成した項目の追加、Consume Adapter Service)<br /><br /> **WCF LOB アダプター開発ウィザード**<br /><br /> (新しい、ファイル、プロジェクト、Visual C#、WCF LOB Adapter)|  
|ドキュメント|\<Installation Folder\> \Documents\WCFLOBAdapterSDK.chm|このファイルには、概念およびこのリリースのマネージ リファレンス コンテンツが含まれています。|  
|製品 Id のファイル|\<Installation Folder\>\Documents\pid.txt|このファイルには、WCF LOB Adapter SDK の製品識別子が含まれています。 マイクロソフト カスタマー サービス & サポート (CSS) に接続するときに、参照としてこの製品識別子を使用します。|  
|サンプル|\<インストール フォルダー\> \Documents\Samples\ContosoAdapterSample.zip<br /><br /> \<インストール フォルダー\> \Documents\Samples\EchoAdapterSample.zip|Samples フォルダーには、2 つのサンプルのアダプターが含まれています。Contoso のアダプターとエコー アダプター。|  

## <a name="privacy"></a>プライバシー
Microsoft は、エンドユーザーのプライバシーの保護に努めています。 使用するアダプターをビルドすると[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]エンドユーザーのプライバシーの影響を与える可能性があります。 たとえば、アダプターの収集し、ユーザーの資格情報を送信することがあります明示的にまたは、送信し、基幹業務システムから機密情報が表示されること可能性があります。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]に送信しませんについては、Microsoft アプリケーションから私たちに送信するか、ユーザーを選択しない限りです。  
  
### <a name="windows-communication-foundation-privacy"></a>Windows Communication Foundation Privacy  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の拡張機能は、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]ようが提供するサービスの多くに依存しています。 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プライバシーを参照してください[Windows Communication Foundation のプライバシー情報](https://msdn.microsoft.com/library/ms733927.aspx)します。  
  
### <a name="microsoft-wcf-lob-adapter-sdk-privacy"></a>Microsoft WCF LOB アダプター SDK のプライバシー  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は API です。 開発者は、使用できるカスタム ログとデバッグを容易にする機能をトレース、チューニングと、アダプターでの監査を作成します。 このような機能を用意する場合は、情報が記録されます、方法についてを制限するため、のみ承認された個人がアクセスの種類を検討する必要があります。 次の必要があります。  
  
-   設定と保守の適切なファイル ログとトレース ファイルに対する制御リスト (Acl) にアクセスします。  
  
-   ファイルに書き込まれる前に、機密データをフィルター処理します。  
  
-   ファイルに書き込まれる前に、機密データを暗号化します。  