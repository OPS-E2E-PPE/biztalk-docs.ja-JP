---
title: "Readme と WCF LOB Adapter SDK でプライバシー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 539a88f9-ce59-46e6-8c9a-418484eabff4
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b0e66bb7f13fd0a7cc39e983ac891708183662b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="readme-and-privacy-in-the-wcf-lob-adapter-sdk"></a>Readme と WCF LOB Adapter SDK のプライバシー
Windows Communication Foundation (WCF) 基幹業務 (LOB) アダプター ソフトウェア開発キット (SDK)  
  
## <a name="inside-the-sdk"></a>SDK 内  
 次の表は、WCF LOB Adapter SDK 内のさまざまなコンポーネントの内容、\<インストール フォルダー\>セットアップ後にします。  
  
|型|場所|Description|  
|----------|--------------|-----------------|  
|実行時|\<インストール フォルダー\> \Bin\Microsoft.ServiceModel.Channels.dll<br /><br /> \<インストール フォルダー\> \Bin\Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse.dll|これらのアセンブリには、ツール内で使用されるメイン フォームのコンポーネントを含むランタイム ベースが含まれています。|  
|ツール|\<インストール フォルダー\> \Tools\Microsoft.ServiceModel.Channels.Tools.PlugInPackage.dll<br /><br /> \<インストール フォルダー\> \Tools\Microsoft.ServiceModel.Channels.Tools.BizTalkExtension.dll<br /><br /> \<インストール フォルダー\> \Tools\Microsoft.ServiceModel.Channels.Wizards.dll|**アダプター サービス参照を Visual Studio プラグインの追加します。**<br /><br /> (.NET プロジェクト [右]、アダプター サービス参照の追加)<br /><br /> **アダプターを使用する BizTalk プロジェクト アドインでは、サービス**<br /><br /> (BizTalk プロジェクト [右]、アダプター サービスの追加、生成した項目の追加)<br /><br /> **WCF LOB アダプター開発ウィザード**<br /><br /> (ファイル、新しい、プロジェクト、Visual C# の場合、WCF LOB Adapter)|  
|ドキュメント|\<インストール フォルダー\> \Documents\WCFLOBAdapterSDK.chm|このファイルには、概念説明し、このリリースのマネージ リファレンス コンテンツが含まれています。|  
|製品 Id のファイル|\<インストール フォルダー\>\Documents\pid.txt|このファイルには、WCF LOB Adapter SDK の製品識別子が含まれています。 Microsoft カスタマー サービスおよびサポート (CSS) に接続するときに、参照としてこの製品識別子を使用します。|  
|サンプル|\<インストール フォルダー\> \Documents\Samples\ContosoAdapterSample.zip<br /><br /> \<インストール フォルダー\> \Documents\Samples\EchoAdapterSample.zip|サンプル フォルダーには、2 つのサンプル アダプターが含まれています。 Contoso エコー アダプターとアダプター。|  

## <a name="privacy"></a>プライバシー
Microsoft は、エンドユーザーのプライバシーの保護に努めています。 使用するアダプターをビルドすると[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]エンドユーザーのプライバシーの影響を与える可能性があります。 たとえば、アダプターの収集し、ユーザーの資格情報を送信することがあります明示的にしたり、可能性があります送受信の機密情報基幹業務システムからです。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]からは送信されず、情報を Microsoft アプリケーション弊社に送信するか、ユーザーを選択しない限りです。  
  
### <a name="windows-communication-foundation-privacy"></a>Windows Communication Foundation のプライバシー  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張である、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]よう提供サービスの多くに依存します。 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プライバシーを参照してください[Windows Communication Foundation のプライバシー情報](https://msdn.microsoft.com/library/ms733927.aspx)です。  
  
### <a name="microsoft-wcf-lob-adapter-sdk-privacy"></a>Microsoft WCF LOB アダプター SDK プライバシー  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] API です。 開発者は、使用できるカスタム ログ記録とトレース、デバッグを容易にする機能、チューニングし、アダプターで監査を作成します。 このような機能を用意する場合を記録する情報と方法についてはできるように制限する承認されたのみ個人にアクセスの種類を検討する必要があります。 次があります。  
  
-   設定して、適切な保守のアクセス制御リスト (Acl) ログおよびトレース ファイル。  
  
-   ファイルに書き込まれる前に、機密データをフィルター処理します。  
  
-   ファイルに書き込まれる前に、機密データを暗号化します。  