---
title: Dreammaker-report-5
author: ''
date: '2020-03-01'
slug: dreammaker-report-5
categories: []
tags: []
image:
  caption: ''
  focal_point: ''
---



# 1. 오늘의 To-do List (목록)

- [x]  우분투에서 EC2 인스턴스 연결
- [x]  FileZilla ftp서버  연결
- [ ]  클라이언트에서 서버에 요청할 형식들 구성 논의
- [ ]  서버에서 클라이언트에 보내줄 형식들 구성 논의
- [ ]  시퀄라이즈에서 mysql curd 명령어 생각,  JOIN 문 등
- [ ]  클라이언트 초기 화면 핸들링 후에 첫 P/R 보내기
- [ ]  비회원 전용 테이블 스키마 설계
- [ ]  설문 시작전 선택할 데이터들에 대한 값 보내는 방법 논의

# 2. 오늘 논의 한 일

- EC2 연결한 민재님 컴퓨터에서 우분투가 잘 못되어 다시 설치 후에 EC2를 연결하였는데 서버와 연결이 잘 되지 않음 → 보안 설정 후 문제 해결
- Filezilla를 통해 EC2에서 CLI작업 보다 편하게 하고 싶어서 연결시도 하였으나 계속 접속 실패 → 우분투 지우기 전에는 잘 되었으나, 현재 Filezilla와 연결이 되질 않음,
- 각 팀원들 전부 FIleZilla를 설치하고 pem키를 통해 서버 연결하는 것 성공, 민재님도 지우고 다시 새 서버 만들기를 통해 연결 성공